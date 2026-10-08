📋 TECH-342 — Order history

Description:
Registered users can see a list of their past orders, filter it by status and by
date range, and open any order to view its details. The list is paginated, 10
orders per page, newest first.

Acceptance criteria:
AC-1  On the account page, clicking "Order history" navigates the user to the
      order-history page, which lists the user's orders newest first with order
      number, date, status and total for each.
AC-2  The list shows 10 orders per page; when the user has more than 10 orders,
      pagination controls appear and the user can move between pages.
AC-3  Selecting a status in the status filter and clicking "Apply" shows only
      orders with that status; the status filter offers all statuses.
AC-4  Entering a date range and clicking "Apply" shows only orders placed within
      that range, inclusive.
AC-5  Clicking "View details" on an order opens that order's details page.
AC-6  A user with no orders sees an empty-state message with a link to the
      catalogue.

Out of scope:
- Guest (not logged-in) users
- Downloading invoices
- Reordering from history
