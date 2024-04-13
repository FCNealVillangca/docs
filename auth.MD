# To Check List for Basic Authentication:
## sign up
### on load
- [ ] if auth redirect to homepage with a flash message "you're already signed in"
### on submit
- [ ] check if all fields are valid and not empty
- [ ] activate loading on submit 
- [ ] check if email exist if yes return an error message under email field and turn off loading.
- [ ] check if user exist if yes return an error message under username field and turn off loading.
### database
- [ ] save the email and password on the accounts table.
- [ ] save the username, about, first name and lastname on the user table.
### on error
- [ ] redirect to "/", return flash a error message
### on success
- [ ] redirect to "/", send email verification link, and flash a success message
## sign in
### on load
- [ ] when routing to sign in page add "?previous=< currentpath >"
- [ ] if auth redirect to homepage with a flash message "you're already signed in"
### on submit
- [ ] check if all fields are valid and not empty
### on error
- [ ] check if the email and password match and if not return flash error message that the password or email is invalid
### on success
- [ ] after signing in redirect to the value of ?previous=< url > or "/"
- [ ] if user is not verified redirect to resend verification with flash message 
- [ ] if user is verified and doesn't have a user in database redirect to update profile page

## resend verification
### on load
- [ ] if not auth redirect to sign in with error flash message "you're not logged in"
- [ ] when routing to sign in page add "?previous=< currentpath >"
- [ ] if already verified redirect to "/" with flash success message "your account is already verified"
### database
- [ ] update the verified field to true
### on error
- [ ] if there is an error redirect to "\" with error flash message "something went wrong"
### on success
- [ ] redirect to home with success flash message
## verify email
### on load
- [ ] if no verifytoken in url params return 404
- [ ] if token is expired return "verify email token is expired"
- [ ] if token is invalid return "verification is invalid"
- [ ] if success redirect to sign in page if not auth or in home if auth with flash message "verification email success"
## forgot password
### on submit
- [ ] check if all fields are valid and not empty
- [ ] activate loading on submit 
### on errror
- [ ] return a flash error message
### on success
- [ ] redirect to home and flash a "please check your email for the reset link" success message.
## reset password
### on load
- [ ] if no resetToken in url params return 403
- [ ] if resetToken is expired return "reset password is expired try again later"
### on submit
- [ ] check if all fields are empty
- [ ] activate loading on submit 
### on errror
- [ ] redirect to "/" and flash an error message
### on success
- [ ] redirect to login and return a success flash message
## change password
### on load
- [ ] if not auth redirect to sign in and flash an error message
### on submit
- [ ] check if the password fields are empty.
- [ ] check again if token is still valid before submitting
- [ ] if the old password is incorrect return a field error
- [ ] activate loading on submit 
### database
- [ ] update the password.
### on error
- [ ] return a flash error message
### on success
- [ ] if success flash a message without redirect.
- [ ] reset all fields.
- [ ] turn off loading.

## edit profile
### on load
- [ ] if not auth redirect to sign in and flash an error message
### on crop avatar
- [ ] check if the file is a valid image.
### on submit
- [ ] check if the fields are empty.
- [ ] check again if token is still valid before submitting
- [ ] activate loading on submit 
### on error
- [ ] redirect to "/" and flash an error message.
- [ ] turn off loading.
### on submit
- [ ] if success flash a message without redirect.
- [ ] turn off loading.