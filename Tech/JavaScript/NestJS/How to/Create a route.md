---
aliases: 
created: 2022-01-18, 4:29:10 pm (Tuesday, January 18th)
updated: 2022-01-19, 3:05:20 pm (Wednesday, January 19th)
---
One part of this is creating a controller using the `Controller` and HTTP verb decorators:
```typescript
// in languages.controller.ts
@Controller('languages')
export class LanguagesController {
    @Get()
    findAll(): string { return "hello world" }
}
```

**NOTE:** Responses return a *status code* of *200* by *default unless* the request is a *POST* request.

The other part is making sure the controller is associated with a *module*:
```typescript
// in languages.module.ts
@Module({
    controllers: [LanguagesController]
})
export class MyModule {}
```

The last part is making sure the module is imported at the *root* module:
```typescript
// in app.module.ts
@Module({
    import: [MyModule]
})
export class AppModule {}
```