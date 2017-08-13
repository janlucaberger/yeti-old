# Schema Information

## teams
column name     | data type | details
----------------|-----------|-----------------------
id              | integer   | not null, primary key
teamname        | string    | not null, unique, indexed
description     | description |
image_avatar    | string    |
private         | boolean   | (default to true)

## users
column name     | data type | details
----------------|-----------|-----------------------
id              | integer   | not null, primary key
firstname       | string    | not null
lastname        | string    | not null
email           | string    | not null, indexed, unique
image_avatar    | string    |

## users_teams
column name     | data type | details
----------------|-----------|-----------------------
id              | integer   | not null, primary key
user_id         | integer   | not null
team_id         | integer   | not null
user_permission_type_id    | integer   | not null
status          | string    | not null
** Index unique on user_id and team_id

## user_permission_types
column name     | data type | details
----------------|-----------|-----------------------
id              | integer   | not null, primary key
type            | string    | not null


## sessions
column name     | data type | details
----------------|-----------|-----------------------
id              | integer   | not null, primary key
user_id         | integer   | not null, foreign_key
session_token   | string    | not null, indexed, unique


## projects
column name     | data type | details
----------------|-----------|-----------------------
id              | integer   | not null, primary key
title           | string    | not null
description     | string    |
status          | string    | not null


## project_sprint
column name     | data type | details
----------------|-----------|-----------------------
id              | integer   | not null, primary key
title           | string    | not null
description     | string    |
status          | string    | not null



## status_types
column name     | data type | details
----------------|-----------|-----------------------
id              | integer   | not null, primary key
type            | string    | not null


## issues
column name     | data type | details
----------------|-----------|-----------------------
id              | integer   | not null, primary key
project_id      | integer   | not null, foreign_key
title           | string    | not null
description     | string    | not null
status_type_id  | string    | not null, foreign_key (Default to Open)
priority        | integer   | (Scale 1 - 5)(Default to 3)

## issues_users
column name     | data type | details
----------------|-----------|-----------------------
id              | integer   | not null, primary key
issue_id        | integer   | not null, foreign_key
user_id         | string    | not null, foreign_key
