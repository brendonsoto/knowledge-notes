---
aliases: 
created: 2022-01-18, 4:31:53 pm (Tuesday, January 18th)
updated: 2022-01-18, 4:36:04 pm (Tuesday, January 18th)
---

- Create a controller
- Add the route name inside the HTTP decorator
    - e.g. To create a */users/me* route:
        ```javascript
        @Controller('users') // Establishes the /users part
        export class UsersController {
            @Get('me')
            findMe(): { ... }
        }
        ```

## Sources
- https://docs.nestjs.com/controllers#routing