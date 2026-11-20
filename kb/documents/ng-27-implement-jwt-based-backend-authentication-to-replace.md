---
type: Document
title: 'NG-27: Implement JWT-based backend authentication to replace localStorage-only
  session'
description: 'Source: NG-27 Implement JWT-based backend authentication to replace
  localStorage-only session Type: Story Status: To Do Labels: BackEnd As a platform
  operator, I want all API routes to be protected by'
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-27: Implement JWT-based backend authentication to replace localStorage-only session

Source: NG-27

Implement JWT-based backend authentication to replace localStorage-only session

Type: Story
Status: To Do
Labels: BackEnd

As a platform operator,
I want all API routes to be protected by a signed JWT token,
So that only authenticated users can access graph data and multi-tenant data is isolated by org.

Description 

Currently the frontend stores session data in localStorage (pnog-session) and the FastAPI backend has no authentication middleware. This means any client with network access can call any API endpoint regardless of org membership.
This story adds JWT-based authentication: POST /auth/login returns a signed token, all FastAPI routes are gated by a JWT dependency, and the token includes org_id and role claims for multi-tenant enforcement. The token is stored in an httpOnly cookie — not localStorage.

Acceptance Criteria 
POST /auth/login accepts username + password, returns a signed JWT in an httpOnly cookie.

All FastAPI routes (both service/backend and pnog/api) are gated by a JWT dependency that validates signature and expiry.

JWT payload includes: user_id, org_id, role (owner/admin/member/viewer), exp.

Routes for org A return 403 if the token's org_id does not match — cross-tenant access blocked.

Frontend redirects to /login on receiving a 401 from any API call.

Existing pnog-session localStorage flow is migrated — login page sets the httpOnly cookie instead.

Token expiry is 8 hours. Refresh token mechanism (POST /auth/refresh) extends session without re-login.
