# To reproduce bug

Follow the following steps to reproduce

- `npm install`
- `npm run dev`
- Go to `localhost:3000` where the app is running
- Click on any of the two tabs
- In the IDE (In my case VSCode) go to `Tab1.vue` or `Tab2.vue` (any will work)
- Comment out the `console.log` in the script or uncomment it
- Save the page and wait for Vite to reload the module.

The following bug should appear:
In yellow: [Vue warn]: Unhandled error during execution of scheduler flush. This is likely a Vue internals bug.
In red: Uncaught (in promise) TypeError: parentComponent.ctx.deactivate is not a function
