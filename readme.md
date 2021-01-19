# Drixit React-Native challenge

The task is to implement a log in screen and show the user info if the login succeed.
There is no UX or UI constraints, this is up to you to decide. You can use [mongodb page](https://account.mongodb.com/account/login) as a sample for the login.

### First screen login

If the user enters a valid mail, then the password input shows up. Just like mongodb login works.
If the email and password are valid, this endpoint returns a valid token (for this demo you can just use a string 'jwt-token').

```
ENDPOINT: USER INFO

POST /api/v0/authenticate
{
	"email": "it@drixit.com",
	"password": "some-password",

} => Promise<{ "jwt": "jwt-token" }>
```

### Second screen: user-info
Use the token to fetch the user info and show the user info in a new screen.
The User information that we need to collect is described in the UserClient interface at [users.ts](https://github.com/Drixit/challenge-rn/blob/main/users.ts)

```
ENDPOINT: USER INFO

GET /api/v0/users/me { "token": "jwt-token" } => Promise<UserClient>
````

There is a dummy `users` file which exports the valid users.
Use this file to validate email vs password, and to fetch the user info.

The focus should be on code style and the way you approach the problem implementation wise.
Feel free to use any other helper library although ideally the more code you write yourself the better.

### Implementation requirements:
- Use React-Native.
- Use a router if you need to render both screens ( log in / user info )
- Feel free to use `react-native init`, `expo init` or other tool.
- Store the user token so if the user reopen the app there is no need to log in again.
- Add a sign out button on user-info screen.
- Handle errors in login Wrong email / password
- Mock `/authenticate` and `/me` api calls simulate server logic (use `users.ts` data).

### Bonus points
- Make it work on different screen sizes
- Use a statically typed language like Typescript
- Use expo to share the app

### The process is as important as the final result, that's why we ask you to:
- Keep (and share) a log of the most important decisions you made at the end of the exercise.
- Deliver your solution as a github repository with enough context and information so it can be analyzed/tested by our team.
- Include everything that you consider relevant when you are about to send the results.

Any questions please contact me via email.
