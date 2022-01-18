# Special routes

## '404' Error

To see special routes, use the switcher.

It is used to render errors, if an application with the `Primary` or `Essential` type falls on the page, ILC will not find a match between the address bar and `Route`, `Template` will not be specified in the route chain, etc., ILC will use `Special route`.

![ILC registry special routes switcher](./assets/routes/special-routes-switcher.png)

- This error usually means that the requested resource was not found on the server.

- When using `Special route` all standard routes are ignored, including `*` with any `Order pos`

- `Special route` must have a `Template`.

- `Special route` must be created separately for each domain.

## Examples:

- Let's go to the `/wrapper/blablabla/` route, ILC will render [Error](../global_errors_handling.md#404-error-not-found), because the specified route does not exactly match our routes, аnd all other routes (like `*`) will be ignored (in this case `navbar` it's part of [Error](../global_errors_handling.md#404-error-not-found), **not** our route `*` with `Order pos - 100`).

![ILC registry second example](./assets/routes/route.png)

**Result:**

![ILC registry fourth example result](./assets/routes/fourth-case-result.png)

## '500' Error

This error is a simple HTML template.
It is designed in such a way that ILC can render it under any conditions.

![ILC registry 500 Error](./assets/routes/500-error.png)

