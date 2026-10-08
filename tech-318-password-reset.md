📋 TECH-318 — Password reset flow
Title:
 TECH-318 — Password reset flow
Description:
Registered users who have forgotten their password should be able to request a reset link via their email address. The reset link should be time-limited and single-use. After a successful reset, the user can log in with their new password.
Acceptance criteria:
Tag
Criterion
AC-1
On the login page, clicking "Forgot your password?" navigates the user to the password reset request page.
AC-2
When a user submits a registered email address on the reset request page, they receive a confirmation message ("If this email is registered, you'll receive a reset link shortly.") and a reset email is sent to that address.
AC-3
The reset link in the email expires after 60 minutes and can only be used once.
AC-4
When a user follows a valid reset link, they are presented with a form to enter and confirm a new password. On submission with matching passwords that meet the site password policy, the password is updated and the user is redirected to the login page with a success message.
AC-5
After a successful password reset, the user can log in with the new password. The old password no longer works.
Out of scope:
Social / OAuth accounts (no password to reset)
Admin-forced password reset
Password reset via SMS
