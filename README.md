# Teampulse

## API Documentation

- **POST** requests pass parameters in JSON format in **Body**, mostly data from forms
- **GET** requests pass parameters that are part of the URL (route)

| URI                 | METHOD | INPUT                                                                   | OUTPUT                                                                   |
| ------------------- | ------ | ----------------------------------------------------------------------- | ------------------------------------------------------------------------ |
| company/create      | POST   | `name`, `description`, `owner`, `users[] {id}`                          | `awid`, `name`, `description`, `owner`, `users[] {id}`                   |
| company/get         | GET    | `awid`                                                                  | `awid`, `name`, `description`, `owner`, `users[] {id}`                   |
| company/update      | POST   | `awid`, `name`, `description`, `owner`, `users[] {id}`                  | `awid`, `name`, `description`, `owner`, `users[] {id}`                   |
| company/view        | GET    | `awid`                                                                  | `workspaces[] { awid, name, description, owner, users[] {id} }`          |
| company/addUses     | GET    | `awid`, `userId`, `roles`                                               | `id`, `firstname`, `lastname`, `email`, `superAdmin`, `roles`, `active`  |
| company/deleteUsers | GET    | `awid`, `userId`                                                        | `id`, `firstname`, `lastname`, `email`, `superAdmin`, `roles`, `active`  |
|                     |        |                                                                         |                                                                          |
| workspace/create    | POST   | `awid`, `name`, `description`, `owner`, `members[] {id}`                | ` awid`, `id `, `name`, `description`, `owner`, `members[] {id}`         |
| workspace/get       | GET    | `id`                                                                    | `id`, `name`, `description`, `owner`, `members[] {id}`                   |
| workspace/update    | POST   | `id`, `name`, `description`, `owner`, `members[] {id}`                  | `id`, `name`, `description`, `owner`, `members[] {id}`                   |
| workspace/delete    | POST   | `id`                                                                    | `id`, `name`, `description`, `owner`, `members[] {id}`                   |
| workspace/view      | GET    | -                                                                       | `workspaces[] { id, name, description, owner, members[] {id} }`          |
|                     |        |                                                                         |                                                                          |
| task/create         | POST   | `worspaceId`, `name`, `description`, `solver`, `deadline`, `status`     | `worspaceId`,`id`, `name`, `description`, `solver`, `deadline`, `status` |
| task/get            | GET    | `id`                                                                    | `id`, `name`, `description`, `solver`, `deadline`, `status`              |
| task/update         | POST   | `id`, `name`, `description`, `solver`, `deadline`, `status`             | `id`, `name`, `description`, `solver`, `deadline`, `status`              |
| task/delete         | POST   | `id`                                                                    | `id`, `name`                                                             |
| task/view           | GET    | -                                                                       | `tasks[] { id, name, description, solver, deadline, status}`             |
|                     |        |                                                                         |                                                                          |
| user/registration   | POST   | `firstname`, `lastname`, `email`, `password`                            | `id`, `firstname`, `lastname`, `email`, `superAdmin`, `roles`, `active`  |
| user/get            | GET    | `id`                                                                    | `id`, `firstname`, `lastname`, `email`, `superAdmin`, `roles`, `active`  |
| user/update         | POST   | `id`, `username`, `firstname`, `lastname`, `email`, `password`,`active` | `id`, `firstname`, `lastname`, `email`, `superAdmin`, `roles`, `active`  |
| user/view           | GET    | -                                                                       | `users[] { id, firstname, lastname, email, superAdmin, roles, active }`  |
| user/login          | POST   | `email`, `password`                                                     | `id`, `firstname`, `lastname`, `email`, `superAdmin`, `roles`, `active`  |
| user/logout         | GET    | -                                                                       |                                                                          |
