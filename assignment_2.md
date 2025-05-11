## 📝 Assignment: Build a Node.js RSS-to-Email Application

### 📌 Overview

In this assignment, you will build a modular Node.js application that reads RSS feed URLs from a PostgreSQL database, fetches the latest news from each RSS feed, and sends the news content via email to a list of recipients stored in the database.

You’ll use modern JavaScript (ESM modules), environment variables, PostgreSQL connections, RSS parsers, and email delivery using **nodemailer** and **Mailtrap.io**. The structure of the project must be organized in multiple files with clear responsibilities.

---

### 📚 Requirements & Instructions

#### 🔧 Setup

1. Use **ES Modules (ESM)** syntax for all JavaScript files.
2. Use the `pg` package to connect to your PostgreSQL database.

   * You can create a free PostgreSQL database using **[Supabase](https://supabase.com)** or **[Neon](https://neon.tech)** (500MB free).
3. Create a `.env` file to store environment variables (e.g., database URL, Mailtrap credentials).
4. Create a `config.js` file that imports and exports all environment variables.

   * ✅ **Only** use `process.env` inside `config.js` — not anywhere else in your project!
5. Add a `.env.sample` file with all variable keys (without actual values) to document what environment variables are needed.

---

#### 📦 Packages You Must Use

* `pg` – to connect to PostgreSQL
* A package to parse RSS feeds like `rss-parser` or similar
* `nodemailer` – to send emails

---

### 🛠 Database Schema

You’ll work with two tables:

#### Table: `rss_feeds`

| Column   | Type    |
| -------- | ------- |
| id       | INTEGER |
| rss\_url | TEXT    |

#### Table: `recipients`

| Column | Type    |
| ------ | ------- |
| id     | INTEGER |
| email  | TEXT    |

---

### 🔄 Application Flow

When the app runs, it should perform the following steps:

1. **Fetch RSS URLs** from the `rss_feeds` table.
2. **Parse all RSS feeds** using an RSS parser.
3. **Merge all feed items** into a single data structure.
4. **Create an HTML email template** with the feed data.
5. **Query all recipient emails** from the `recipients` table.
6. **Send the email** to all recipients using `nodemailer` and [Mailtrap.io](https://mailtrap.io/).

   * Read Mailtrap's official guide: [Send Emails with Node.js](https://mailtrap.io/blog/send-emails-with-nodejs/)

---

### 🤖 (Optional) Telegram Bot Extension

As an optional challenge, instead of sending emails, send the news to **Telegram channels**:

1. Store Telegram channel IDs in a `telegram_channels` table (you should create this).
2. Use the **Telegram Bot API** to send the merged news content to all listed channels.
3. Refer to the official [Telegram Bot API](https://core.telegram.org/bots/api) and install any necessary packages (e.g., `node-telegram-bot-api`).

---

### ✅ Final Notes & Tips

* ✅ **Use Git from the start** of your project. Commit every small change!
* ✅ **Push your code to a Git repository** (e.g., GitHub).
* ❌ **Do NOT commit `.env` or `node_modules`**. Add them to `.gitignore`.
* 🧪 Test your app and make sure each module works independently and together.

---

### 📂 Submission

Please submit your GitHub repository link with:

* A clean file structure
* `README.md` explaining how to run your project
* `.env.sample` included
* Proper `.gitignore`

