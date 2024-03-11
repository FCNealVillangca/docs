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

## resend verification
- [ ] return 403 page when not signed in
- [ ] return 403 page when the user is already verified
- [ ] if successful return a success message

## verify email
- [ ] if not auth redirect to login with flash message "you're not logged in"
- [ ] return 403 page when the user is already verified
- [ ] if no verifytoken in url params return 403
- [ ] if token is expired return "verify email token is expired"
- [ ] if token is invalid return "verification is invalid"
- [ ] if success return a congratulations message

## forgot password
- [ ] if auth return 403
- [ ] check if the email field is empty.
- [ ] if there is any 400 error return a "something went wrong" message
- [ ] if success unmount the email field and return a success message

## reset password
- [ ] if no resetToken in url params return 403
- [ ] if no resetToken is expired return "reset password is expired try again later"
- [ ] check if all fields are empty
- [ ] redirect to login and return a success flash message

## change password
- [ ] if not auth redirect to login with flash message "you're not logged in"
- [ ] check if the password fields are empty.
- [ ] if the old password is incorrect return a field error
- [ ] if success flash a message without redirect.

## edit profile
- [ ] if not auth redirect to login with flash message "you're not logged in"
- [ ] check if the fields are empty.
- [ ] check if the image is valid and has valid format.
- [ ] if success flash a message without redirect.