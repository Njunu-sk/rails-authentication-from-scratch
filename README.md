# From [Steve Polito Blog](https://stevepolito.design/blog/rails-authentication-from-scratch/)

#### I'll discuss some of the Security features and countermeasures

## Session Fixation 
- This attack is focused on fixing user's session ID known to the attacker and forcing user's browser into using this ID
- This is solved with the `reset_session`, this issues a new session identifier and declares the old one invalid after a successful login.

- This is demonstrated in the `Authentication` module: login and logout methods both have `reset_session`.
