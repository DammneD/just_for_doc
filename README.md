# Match & cascade merge

## Route match patterns
Important! ILC looks for an exact match on the route, this means that the content with the route `/` will be rendered only on the main page of the application. To bypass this, just add `*` after the route.

![Animation during reroute](./assets/route.png)

- `*` - displayed on all routes by default (if Order pos. and/or Domain name allows).

- `/` - displayed only on the main page of the application.

- `/news/*` - the content will be displayed on the `/news/` route and everything that will be written in the address bar after it(like `/news/blablabla`).

- `/wrapper/` - content will be displayed exclusively on this route, if you add characters in the address bar after the route (like `/wrapper/blablabla`), the content will not be displayed.