# From [Steve Polito Blog](https://stevepolito.design/blog/rails-authentication-from-scratch/)

#### I'll discuss some of the Security features and countermeasures

## Session Fixation 
- This attack is focused on fixing user's session ID known to the attacker and forcing user's browser into using this ID
- This is solved with the `reset_session`, this issues a new session identifier and declares the old one invalid after a successful login.

- This is demonstrated in the `Authentication` module: login and logout methods both have `reset_session`.

## User Management 
- User passwords must be stored only as cryptographic hash.
- This is given in Rails with the `has_secure_password`, which supports secure password hashing, confirmation and recovery mechanism.

- This is included in our `User` model along side `bcrypt gem`.

## Brute force Attack 
- Accounts on the trial and error attack on the login page 

- The best solution to this is to display a generic error message or require to enter a CAPTCHA

## Account Hijacking 

### Passwords 
- In scenarios where hacker is about to reset a user password after session fixation, provide attacker with a field to type current password.

- This makes it more difficult for the attackers.

### Email 
- Require user to enter a password when changing an email

