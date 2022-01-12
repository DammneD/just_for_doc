# Match & cascade merge

## Route field
![ILC registry route](./assets/route.png)

- `*` - displayed on all routes by default (if Order pos. and/or Domain name allows).

- `/` - displayed only on the main page of the application.

- `/news/*` - the content will be displayed on the `/news/` route and everything that will be written in the address bar after it(like `/news/blablabla`).

- `/wrapper/` - content will be displayed only on this route, if you add characters in the address bar after the route (like `/wrapper/blablabla`), the content will not be displayed.

## Order field
![ILC registry Order field](./assets/order-field.png)

- Only integer numbers are allowed, from minus infinity to plus infinity.

- ILC goes through positions from lowest to highest.

- Order positions must be unique for each domain (we can use the same order position, provided that the domain names are different).

## Next field
![ILC registry Next field](./assets/next-field.png)

- It can be set to `true` or `false`

- If it is `true` the ILC will render the content and go to the next route.

- If it is `false` the ILC will render the content and **will not proceed** to the next route.

## Examples:

- Let's say we are trying to access the route `/wrapper/`, in the case as in the screenshot below, ILC will start with the application with the lowest value of `Order pos`, in this case it is `-100`, because its route is `*` it will be rendered, but the `Next` field is set to `false`, So the ILC will not look for matches further, so only one application will be rendered for us.

![ILC registry first example](./assets/route2.png)
**Result:**
![ILC registry first example result](./assets/first-case-result.png)

#

- Now let's change the value of the `Next` field as in the screenshot below, and again try to enter the `/wrapper/`route, ILC will start from the application with the lowest `Order pos` value,
in this case it is `-100`, because its route is `*` it will be rendered, and since the `Next` field is set to `true` ILC will go further along the order, `-1` **will not be rendered** because the `/simple/` route does not match the given one, we move further to position `0`, render this application because its route `*` and move on, because the `Next` field is set to `true`, next few applications will not be rendered, because their route does not match the specified one, until we reach the position `40`, its route exactly matches the specified one, the application will be rendered, and because `Next` is set to the value `false` ILС will not look for matches further. In total, we will render 3 applications, both routes `*` and route `/wrapper/`.

![ILC registry second example](./assets/route.png)
**Result:**
![ILC registry second example result](./assets/first-case-result.png)



