## Module Providers

You can create module providers, such as Notification or File Module Providers under a sub-directory of this directory. For example, `src/providers/my-notification`.

Then, you register them in the Acmekit application as `plugin-name/providers/my-notification`:

```ts
module.exports = defineConfig({
  // ...
  modules: [
    {
      resolve: "@acmekit/medusa/notification",
      options: {
        providers: [
          {
            resolve: "@myorg/plugin-name/providers/my-notification",
            id: "my-notification",
            options: {
              channels: ["email"],
              // provider options...
            },
          },
        ],
      },
    },
  ],
})
```

Learn more in [this documentation](https://docs.acmekit.com/learn/fundamentals/plugins/create).
