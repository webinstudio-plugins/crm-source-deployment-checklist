# CRM source deployment checklist

Review these questions with the developer who will install and operate Soft Studio CRM Pro. Webin Studio develops and sells the product. This free guide contains planning documents; the paid application source is supplied through its product page.

## 1. Choose the source that fits your project

Soft Studio CRM is a USD29 browser-local HTML/CSS/JavaScript frontend. Its [fictional-record demo](https://demo.webinstudio.co.kr/demo/?utm_source=github&utm_medium=community) shows that edition.

[Soft Studio CRM Pro](https://contra.com/products/mFDXNV5A-soft-studio-crm-pro-nextjs-supabase-source) is USD79 one-time source for a Next.js/React/Supabase workspace. You install it in your own accounts. Its interface is in English and uses USD. The browser-local demo does not demonstrate Pro's authentication, database or deployment.

## 2. Check the application host

Pro needs server execution for authentication callbacks, Server Actions and mutation routes. Choose a Node-capable Next.js host or a suitable Node server behind HTTPS. A static-only host does not run those workflows. [Next.js deployment documentation](https://nextjs.org/docs/app/getting-started/deploying) distinguishes server deployment from limited static export.

The supplied local setup requires Node.js 22.18 or newer and a running Docker-compatible engine. Use the package lockfile and the installation guide in the purchased source. Local Supabase services are development tools, not a production hosting package.

## 3. Confirm account email delivery

Assign an SMTP provider and sender-domain owner, then test signup confirmation and password recovery with actual inboxes on the final domain. Local Mailpit captures messages without delivering real email.

Supabase's default mail service restricts recipients and is not intended for production. Review its current [custom SMTP requirements](https://supabase.com/docs/guides/auth/auth-smtp). A local preview or sent request does not prove inbox delivery. Provider fees and limits are separate from the source price.

## 4. Keep workspace access checks in place

Pro uses server-side account checks and PostgreSQL row-level security. Plan a separate staging check with two workspaces and the owner, admin and member roles. Verify that each account can perform its intended actions and cannot read another workspace's records.

Do not disable RLS or expose elevated keys to get past an access error. The application configuration uses a publishable key. [Supabase's RLS documentation](https://supabase.com/docs/guides/database/postgres/row-level-security) explains access policies and why secret keys must stay out of the browser. This planning sheet does not run or certify those checks.

## 5. Check the collaboration behavior

Team invitation links are delivered manually through your own channel. Invited colleagues verify their accounts before joining. Other users see saved changes after Refresh or reloading. If automatic invitation mail or live push synchronization is required, scope that work before buying.

## 6. Plan a restorable backup

CSV exports support analysis; they do not preserve accounts, permissions and complete relationships. Pro's legacy JSON import moves compatible browser-local records into Pro. It is not a complete Pro backup/restore facility.

Assign a database backup and restoration owner. Account users, application data and deployment configuration need appropriate recovery procedures. Test restoration in an isolated environment using the provider's supported process; read the purchased BACKUP.md before operating a live project.

## 7. Separate staging and production

Confirm the intended database project before inspecting and applying migrations. Use the exact production origin and callback configuration described in DEPLOYMENT.md. Test final-domain cookies, redirects, email delivery and role changes separately from localhost checks. Keep fictional sample records in staging.

## 8. Assign operating costs and responsibilities

The USD79 purchase licenses one personal or client end product. Hosting, Supabase, SMTP, domains, backups and ongoing operations are the buyer's responsibility. Original-source installation questions and reproducible bugs are covered for 14 calendar days after purchase through Contra product/purchase messages. Custom deployment, live migration and ongoing maintenance are outside that included scope. Template redistribution or resale is not permitted; the product license and platform purchase terms apply.

Copy [the blank review sheet](PLANNING-NOTES.md) and complete it privately with your developer. Keep credentials, private keys, customer exports and completed sensitive project notes out of public repository issues.

Product scope and linked provider documentation reviewed October 9, 2026. Provider plans and limits can change. Prepared by Webin Studio with AI assistance. Completing this guide does not prove a successful deployment or purchase.
