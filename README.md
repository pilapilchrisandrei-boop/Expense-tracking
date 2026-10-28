
# Expenses Tracking — Personal Finance Tracker

A lightweight, intuitive, and secure personal finance management mobile application for Android. Built with an offline-first architecture, **Expenses** enables users to log daily purchases, track cash flow, categorize expenditures, view monthly summaries, and maintain strict adherence to personal budgets—all without storing data on third-party cloud servers.

---

## 📌 Problem Statement

Managing personal finances manually or using complex, cloud-dependent financial apps often introduces key friction points:

1. **Privacy Concerns:** Users are reluctant to sync bank accounts or store transaction histories on third-party servers.
2. **Friction & Complexity:** Cluttered dashboards, mandatory accounts, and subscription models create steep learning curves.
3. **Lack of Proactive Awareness:** Without instant alerts, users frequently cross their monthly spending limits unnoticed.

---

## 🎯 Target Users

* **Budget-Conscious Individuals:** Students and young professionals looking to log daily expenses and stay within a monthly allowance.
* **Privacy-Focused Users:** Anyone who prefers a completely offline tool that keeps financial data local to their device.
* **Small Business Owners & Freelancers:** Users who need fast entry and instant text-based receipt generation for client transactions.

---

## 💡 Proposed Solution

* **Works Fully Offline:** Your data stays on your phone using local storage. Nothing gets uploaded to the cloud or shared online.
* **Fast Expense Entry:** Simple layout designed so you can open the app, log an expense in seconds, and get back to your day.
* **Budget Warning Notifications:** Automatically alerts you when your total monthly spending crosses your set limit.
* **Receipts & Monthly Summaries:** Quickly share plain-text receipts and view monthly reports broken down by spending categories (like Food, Transport, etc.).

---

## 🎯 Objectives, Scope & Limitations

### General Objective
To develop a robust, secure, and user-friendly Android application that enables users to effortlessly record, categorize, monitor, and analyze their daily and monthly expenses while maintaining absolute local data privacy and proactive budget control.

### Specific Objectives
1. Implement a reliable local SQLite database storage engine for CRUD operations on expense records.
2. Design an intuitive dashboard that aggregates total expenses and renders transaction history dynamically using `RecyclerView` and `ExpenseAdapter`.
3. Provide granular categorization and monthly statistical reporting (`ReportActivity`).
4. Implement proactive budget monitoring (`NotificationHelper`) that triggers Android notification alerts when monthly limits are exceeded.
5. Enable instant receipt formatting and sharing via standard Android `Intent.ACTION_SEND`.

---

### 🔍 Scope vs. Limitations

| **Scope** | **Limitations** |
| :--- | :--- |
| Local expense record creation, deletion, and retrieval | Single-user application without multi-currency conversion or cloud sync |
| Category-based expenditure sorting and grouping | Fixed default monthly budget threshold (expandable via configuration) |
| Monthly spending summary calculations and budget threshold alerts | Local storage only (data is tied to the device installation) |
| Native Android notification handling supporting Android 13+ (`POST_NOTIFICATIONS` runtime permissions) | |
| Plain-text receipt sharing | |

---

## ✨ Major Features

1. **Dashboard Overview:** Displays total current spending and an empty-state indicator when no records exist.
2. **Expense Addition:** Form validation for titles and numeric amounts combined with category selection spinners.
3. **Monthly Reporting:** Aggregated monthly totals and breakdown of spending by category (e.g., Food, Transport, Utilities, etc.).
4. **Interactive Expense Management:**
   * **Confirmation Dialogs:** Safe deletion flow requiring user confirmation.
   * **Receipt Sharing:** Builds professional formatted plain-text receipts and launches system share sheets.
5. **Budget Exceeded Notifications:** Automated notification triggers when cumulative monthly expenses exceed the preset budget ($5,000.00).

---

## 🛠️ UI/UX & Technical Stack

### UI/UX Design System
* **Design System:** Material Design 3 guidelines (`Theme.Expenses`), leveraging standard widgets (`ConstraintLayout`, `FloatingActionButton`, `CardView`, `RecyclerView`).
* **Visual Hierarchy:** 
  * **Prominent Total Spending Display:** Positioned at the top of `MainActivity` (`tvTotal`).
  * **Transaction List:** Scrollable chronological list of expense cards (`item_expense.xml`) featuring item titles, categories, dates, formatted currency, and quick action buttons for sharing and deletion.
  * **Floating Action Button:** Immediate access to expense creation (`fabAdd`).
  * **Empty States:** Dynamic visibility handling (`tvEmpty`) when transaction lists are empty.

### Tech Stack & Architecture

| **Category / Layer** | **Technologies Used** |
| :--- | :--- |
| **Development Tools** | Android Studio, Gradle (Kotlin DSL), Git |
| **Core Android SDK & AndroidX** | `AppCompatActivity`, `ConstraintLayout`, `RecyclerView`, Activity KTX, Core KTX, Notifications Compat |
| **Persistence & Utilities** | Android SQLite API (`SQLiteOpenHelper`, `ContentValues`), Custom formatting helper (`Fmt`) |

---
