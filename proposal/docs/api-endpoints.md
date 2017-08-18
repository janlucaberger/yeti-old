# Endpoints

<!--
## Sign up
- POST /users { firstname, lastname, email, password_digest}
- POST /sessions

## Create or Join Team
If creating a new team
- POST /teams {teamname, description, image_avatar, private}
- POST /users_teams {user_id, team_id, user_permission_type_id}

If joining a public team
- POST /users_teams {user_id, team_id, status, user_permission_type_id}
  - Default permission type will be set to lowest access
  - Status will be set to ACTIVE

If joining a private team
- POST /users_teams {user_id, team_id, status, user_permission_type_id}
  - Status will be set to PENDING and team owner can approve application


## Dashboard
- GET /projects
- GET /issues (Specifically issues assigned to user)
 -->


## Users
- `POST   /api/users`
  ###### Notes
  - Required params: `first_name, last_name, email`
  - Optional params: `avatar_url`
  - `email` must be unique
  > When creating users their *default permission type will be set to the lowest
  permission settings*. The value can be changed by team admin.

- `PATCH  /api/users`
___

## Teams
- `POST   /api/teams`  
  ###### Notes
  - Required params: `team_name`
  > For the V1 all teams will be set to private. A later feature will be the ability to set teams to public that anyone can join.
  - Optional params: `description, avatar_url`
  - `team_name` must be unique


- `PATCH  /api/teams`
  ###### Notes
  - Allowed params: `description, avatar_url`
  > Team names can not be changed


## Projects
- `POST   /api/projects`
- `GET    /api/projects/`
- `GET    /api/projects/:id`
- `PATCH  /api/projects/:id`
- `DELETE /api/projects/:id`

## Issues
- `POST   /api/issues`
- `GET    /api/issues/:id`
- `PATCH  /api/issues/:id`
- `DELETE /api/issues/:id`

- Comments
- `GET    /api/issues/:id/comments`
- `POST   /api/issues/:id/comments`
- `DELETE /api/issues/:id/comments`

- Votes
- `GET    /api/issues/:id/votes` ** Returns total vote count
- `POST   /api/issues/:id/comments`
- `DELETE /api/issues/:id/comments`

- Watchers
- `GET    /api/issues/:id/votes` ** Returns total watch count
- `POST   /api/issues/:id/comments`
- `DELETE /api/issues/:id/comments`

- History
- `GET    /api/issues/:id/history`

## Sprints





The following routes are mainly for UI for now
## Issue Types
- `GET /api/issue_types`

## Status Types
- `GET /api/status_types`

## User Permission Types
- `GET /api/user_permission_types`
