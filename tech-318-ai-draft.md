Test Step 1
  Source AC:        AC-1
  Precondition:     User is on the login page.
  Action:           Click the "Forgot your password?" link.
  Expected Result:  User is taken to the password reset page.
Test Step 2
  Source AC:        AC-2, AC-3
  Precondition:     User has a registered account.
  Action:           Enter the registered email and submit. Then use the reset link
                    from the email to access the reset form.
  Expected Result:  Confirmation message is shown. Reset link works and takes user
                    to the reset form. If used again or after an hour, it fails.
Test Step 3
  Source AC:        AC-4
  Precondition:     User has a valid reset link.
  Action:           Follow the link, enter a new password, confirm it, and submit.
  Expected Result:  Password is updated and user is redirected to login.
Test Step 4
  Source AC:        AC-5
  Precondition:     User has reset their password.
  Action:           Log in with the new password and try the old one.
  Expected Result:  New password works; old does not.
Test Step 5
  Source AC:        —
  Precondition:     User is on the password reset request page.
  Action:           Submit an email address that is not registered with TechShop.
  Expected Result:  The same confirmation message is shown ("If this email is registered,
                    you'll receive a reset link shortly.") — no indication of whether
                    the account exists.