slug: setcookie
excerpt: Set a browser cookie

Set a browser cookie.

| | |
|--- | --- |
| **Returns** | a cookie object |
| **Timeout** | *cannot timeout* |

***

# [cy.setCookie( *name*, *value* )](#section-usage)

Sets a browser cookie.

***

# Options

Pass in an options object to change the default behavior of `cy.setCookie`.

**[cy.setCookie( *name*, *value*, *options* )](#options-usage)**

Option | Default | Notes
--- | --- | ---
`path` | `/` | the cookie path
`domain` | `window.location.hostname` | the domain the cookie is visible to
`secure` | `false` | whether the cookie is a secure cookie
`httpOnly` | `false` | whether the cookie is an HTTP only cookie
`expiry` | 20 years into the future | when the cookie expires, specified in seconds since [Unix Epoch](https://en.wikipedia.org/wiki/Unix_time).
`timeout` | [`commandTimeout`](https://on.cypress.io/guides/configuration#section-global-options) | Total time to retry the setCookie command
`log` | `true` | whether to display command in command log

You can also set options for all [cy.wait](https://on.cypress.io/api/wait) `requestTimeout` and `responseTimeout` globally in [configuration](https://on.cypress.io/guides/configuration) to control how long to wait for the request and response of the supplied route.

***

# Usage

## Set a cookie

```javascript
cy
  .getCookies().should('be.empty')
  .setCookie('session_id', '189jd09sufh33aaiidhf99d09')
  .getCookie('session_id').should('have.property', 'value', '189jd09sufh33aaiidhf99d09')
```

***

# Command Log

## Get cookie

```javascript
cy
  .getCookies().should('be.empty')
  .setCookie('fakeCookie1', '123ABC')
  .getCookie('fakeCookie1').should('have.property', 'value', '123ABC')
```

The commands above will display in the command log as:

![screen shot 2016-05-10 at 12 15 53 pm](https://cloud.githubusercontent.com/assets/1271364/15153887/00b4c98e-16a9-11e6-8df5-bb2018582439.png)

When clicking on `setCookie` within the command log, the console outputs the following:

![screen shot 2016-05-10 at 12 16 01 pm](https://cloud.githubusercontent.com/assets/1271364/15153886/00b41782-16a9-11e6-99db-bc085c3513b3.png)

***

# Related

- [clearCookie](https://on.cypress.io/api/clearcookie)
- [clearCookies](https://on.cypress.io/api/clearcookies)
- [getCookie](https://on.cypress.io/api/getcookie)
- [getCookies](https://on.cypress.io/api/getcookies)
- [Cypress API Cookies](https://on.cypress.io/api/cookies)