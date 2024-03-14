# To Check List for Basic Authentication
## sign up
- [x] if auth redirect to homepage with a flash message "you're already signed in"
- [x] check if all fields are valid and not empty
- [x] return error 400 w/ "account already exist" under email field if not unique
- [x] redirect to "/", send email verification link, and flash a success message

## sign in
- [ ] when routing to sign in page add "?previous=path"
- [x] if auth redirect to homepage with a flash message "you're already signed in"
- [x] check if all fields are valid and not empty
- [x] return error 400 w/ "password or email is invalid" if password or email doesn't match
- [x] if user is not verified redirect to resend verification with flash message 
- [x] after signing in redirect to the value of ?previous=< url > or "/"

## resend verification
- [x] if not auth redirect to sign in with flash message "you're not logged in"
- [x] when redirecting to sign in page ad '?previous=< url >' to path
- [x] if already verified redirect to home with flash message "your account is already verified"
- [x] if there is an error redirect to home with flash message "something went wrong"
- [x] if success redirect to home with flash message with a success message

## verify email
- [x] if no verifytoken in url params return 404
- [x] if token is expired return "verify email token is expired"
- [x] if token is invalid return "verification is invalid"
- [x] if success redirect to sign in page if not auth or in home if auth with flash message "verification email success"

## forgot password
- [ ] if auth redirect to homepage with a flash message "you're already signed in"
- [ ] check if the email field is empty.
- [ ] if there is any 400 error return a "something went wrong" message
- [ ] if success unmount the email field and return a success message

## reset password
- [ ] if no resetToken in url params return 403
- [ ] if no resetToken is expired return "reset password is expired try again later"
- [ ] check if all fields are empty
- [ ] redirect to login and return a success flash message

## change password
- [ ] if not auth redirect to sign in with flash message "you're not logged in"
- [ ] check if the password fields are empty.
- [ ] if the old password is incorrect return a field error
- [ ] if success flash a message without redirect.

## edit profile
- [ ] if not auth redirect to sign in with flash message "you're not logged in"
- [ ] check if the fields are empty.
- [ ] check if the image is valid and has valid format.
- [ ] if success flash a message without redirect.