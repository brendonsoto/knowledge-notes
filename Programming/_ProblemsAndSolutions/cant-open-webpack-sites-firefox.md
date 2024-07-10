---
created: 2024-07-10T12:09Z
---
# Can't Open Webpack-served Sites on Firefox

Knowing me, if you encounter this again you'll probably look in the network
panel of the dev tools and see `NS_CORRUPTED_CONTENT` or something like that.
That may be a red herring! Look for the root endpoint you're trying to reach.
You may encounter the error `NS_BINDING_ABORTED` for that network request.

The problem has to do with Firefox's security.

To fix:
- Go to Firefox's options (`cmd+,`)
- Under **Enhanced Tracking Protection** click *Manage Exceptions...*
- Add `localhost`
- Disable HTTPS-Only mode
- Under **DNS over HTTPS** click *Manage Exceptions...*
- Add `localhost`
  exception from tracking
