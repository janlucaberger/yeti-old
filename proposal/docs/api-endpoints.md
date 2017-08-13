# Endpoints


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
