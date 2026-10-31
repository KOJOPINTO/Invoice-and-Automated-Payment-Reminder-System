# Workflow Overview

## Project: Invoice & Automated Payment Reminder System

This project automates invoice confirmations and overdue payment reminders for a business using Make.com, Google Sheets, and Gmail.

The system helps businesses keep track of unpaid invoices, notify customers when invoices are recorded, and follow up automatically when payments become overdue.

## Scenario 1: Invoice Confirmation & Owner Notification

**Trigger:** A new invoice is added to Google Sheets.

**Workflow:**
1. Make.com detects the new invoice.
2. Gmail sends an invoice confirmation email to the customer.
3. Gmail sends a notification to the business owner with the invoice details.

## Scenario 2: Automated Invoice Payment Reminders

**Trigger:** The scheduled Make.com scenario runs.

**Workflow:**
1. Make.com searches Google Sheets for invoices marked as `Unpaid` and `Pending`.
2. It checks the due date to identify overdue invoices.
3. Eligible customers receive an automated payment reminder by email.
4. The spreadsheet is updated:
   - Reminder Status changes to `Sent`.
   - Last Reminder Date records when the reminder was sent.

## Data Management

Google Sheets serves as the central invoice tracker. It stores customer details, invoice numbers, amounts, due dates, payment statuses, and reminder history.

## Duplicate Reminder Prevention

After a reminder is sent, the invoice's Reminder Status changes to `Sent`. This prevents the same invoice from being selected again by the reminder workflow.

## Business Value

The automation reduces manual follow-up, improves invoice tracking, saves administrative time, and helps businesses follow up on overdue payments consistently.
