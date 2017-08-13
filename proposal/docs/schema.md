# Schema Information

## users
column name     | data type | details
----------------|-----------|-----------------------
id              | integer   | not null, primary key
firstname       | string    | not null
lastname        | string    | not null
email           | string    | not null, indexed, unique
image_avatar    | string    |

## user_permission_types
column name     | data type | details
----------------|-----------|-----------------------
id              | integer   | not null, primary key
type            | string    | not null

## user_permissions
column name     | data type | details
----------------|-----------|-----------------------
id              | integer   | not null, primary key
user_id         | integer    | not null, unique
permission_type_id  | integer    | not null

## sessions
column name     | data type | details
----------------|-----------|-----------------------
id              | integer   | not null, primary key
user_id         | integer    | not null
session_token  | string    | not null, indexed, unqiue


## projects
column name     | data type | details
----------------|-----------|-----------------------
id              | integer   | not null, primary key
title         | string    | not null
description  | string    |
status         | string    | not null
priority      | integer     | (Scale 1 - 5)(Default to 3)

## project_sprint
column name     | data type | details
----------------|-----------|-----------------------
id              | integer   | not null, primary key
title         | string    | not null
description  | string    |
status         | string    | not null
priority      | integer     | (Scale 1 - 5)(Default to 3)
