---
aliases: 
created: 2022-01-19, 2:27:45 pm (Wednesday, January 19th)
updated: 2022-01-19, 3:01:37 pm (Wednesday, January 19th)
---
## Prerequisities
- `node`
- nestjs cli
    - `npm i -g @nestjs/cli`

## Steps
- open a terminal (*TermA*)
- `nest new <project-name>`
- `cd <project-name>`
- open a new terminal window (*TermB*)
- `cd <path/to/project>`
    - You can use this time to check the scaffolding is fine by running `npm start` in *TermB*. Just make sure to quit the app (`<Ctrl-C>`) when you are done.
- Switch back to *TermA*
- Open the `app.module.ts` file
- Delete the `AppController` and `AppService` references and import statements
- Delete the files for `AppController` ,`AppService`, and the test/spec file
- Run `nest g module <name>`
    - e.g. `nest g module beers` for a Beers module for managing the interface to data about beer
- Run `nest g controller <name>` to add a controller to your new module
    - *NOTE:* `<name>` for creating module and controller (and other pieces related to the module) must be the same. Otherwise Nest will make a new directory and dump the files there.
- Open the new controller file
- Update the top-level import to also import the `Get` decorator
    - `import { Controller } from ...` -> `import { Controller, Get } from ...`
- Add to the class' body:
    ```typescript
    @Get()
    findAll(): string[] {
        return ['a', 'b', 'c']; // Whatever you want
    }
    ```
    - If you want, you can run the program and visit your route (e.g. `/<name>`) to see the array of data returned
- Run `nest g service <name>` to create a file to act as a data provider
- Open the service file
- Move the `findAll` function from the Controller file into the Service
- Open the controller file
- Add a line to import your service
    - `import { <Name>Service } from './<name>.service'`
- Add right under the `export class ...` line:
    ```typescript
    // Format: constructor(private <name>Service: <Name>Service) {}
    // An example using the service "MyService"
    constructor(private myService: Service) {}
    ```
    - If you want, you can run the program and visit your route (e.g. `/<name>`) to see the array of data returned *still*