# Business Rules – Invoice & Automated Payment Reminder System

## 1. Invoice Creation

- Business staff manually enter new invoice records into Google Sheets.
- Each invoice must have a customer name, customer email, invoice number, amount, invoice date, and due date.
- New invoices are recorded with a payment status of `Unpaid`.
- The reminder status is initially set to `Pending`.

## 2. Invoice Confirmation

- When a new invoice is added, Make.com detects the new row.
- The customer receives an invoice confirmation email.
- The business owner receives a separate notification.

## 3. Invoice Eligibility for Payment Reminders

An invoice qualifies for an automated reminder only when both conditions are met:

- Payment Status = `Unpaid`
- Reminder Status = `Pending`

## 4. Overdue Invoice Detection

- Make.com compares the invoice due date with the current date.
- Only invoices with due dates earlier than the current date are considered overdue.
- Invoices due today or in the future are excluded.

## 5. Payment Reminder

- Gmail sends a reminder to the customer's recorded email address.
- The email includes the invoice number, amount due, and due date.

## 6. Reminder Status Update

After the reminder email is sent successfully:

- Reminder Status changes from `Pending` to `Sent`.
- Last Reminder Date records the time the reminder was sent.

## 7. Paid Invoices

- Paid invoices are excluded from reminder processing.
- Their reminder status should be recorded as `Not Required`.

## 8. Duplicate Reminder Prevention

- Invoices marked `Sent` are excluded from future reminder processing.
- This prevents the same invoice from receiving repeated reminders through this workflow.

## 9. Data Accuracy

- Customer and invoice information must be accurate.
- Payment statuses must be updated when customers make payments.
- Due dates must use a consistent date format.

## 10. Current System Scope

The current version sends one automated overdue reminder per invoice. Future versions may introduce multiple reminder stages and payment gateway integration.
