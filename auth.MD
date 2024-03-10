# To Check List for Basic Authentication
## sign up
- [ ] if auth: redirect to homepage with a flash message "you're already signed in"
- [ ] validate fields if empty and flash error message under the field
- [ ] check if all fields are valid and not empty
- [ ] return error 400 w/ "account already exist" under email field if not unique
- [ ] redirect to "/" if success

## sign in
- [ ] when routing to sign in page add "?previous=path"
- [ ] if auth: redirect to homepage with a flash message "you're already signed in"
- [ ] check if all fields are valid and not empty
- [ ] return error 400 w/ "password or email is invalid" if password or email doesn't match
- [ ] after signing in redirect to the value of ?previous=< url > or "/"

## verify email
- [ ] if not auth return 403
- [ ] if no verifytoken in url params return 403
- [ ] if token is expired return "verify email token"
- [ ] if token is invalid return "verification is invalid"
- [ ] if success return a congratulations message

## resend verification
- [ ] return 403 page when not signed in
- [ ] return 403 page when the use is verified
- [ ] if successful return a success message

## forgot password
- [ ] if auth return 403
- [ ] if auth return 403

