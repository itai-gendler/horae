---
domain: invoices
availability:
- {place: 'web::team'}
references:
- kind: code
  role: implementation
  target: crates/horae/src/reports.rs#export_invoice_csv
- kind: code
  role: implementation
  target: crates/horae/src/reports.rs#export_invoice_xlsx
- kind: code
  role: implementation
  target: crates/horae/src/pages/invoices.rs#InvoiceDetail
---

# Export invoice

A manager or admin downloads an invoice as PDF, CSV or XLSX.
