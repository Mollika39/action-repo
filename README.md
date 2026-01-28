action-repo 🚀

GitHub Actions Webhook Trigger Repository

📌 Overview

action-repo is a GitHub repository created as part of the Developer Assessment Task.
Its sole, noble responsibility is to generate GitHub events and send them to a webhook endpoint (webhook-repo) using GitHub Webhooks.

This repository does not contain backend logic, databases, or UI code.
Think of it as the bell — it rings; the webhook-repo listens.

🎯 Purpose

This repository triggers GitHub webhook events for the following actions:

✅ Push

✅ Pull Request

✅ Merge (via merged pull requests)

These events are sent automatically to a registered webhook endpoint, where they are:

Captured by a Flask server

Stored in MongoDB

Displayed on a UI (handled entirely in webhook-repo)

🔔 Webhook Events Enabled

The following GitHub events are enabled in this repository:

Push

Pull Requests

Merge Group (optional, brownie points 🍫)

Each event sends a payload to the webhook endpoint containing:

Author name

Source branch

Target branch

Timestamp

⚙️ Webhook Configuration

The webhook for this repository is configured as follows:

Payload URL

https://<your-ngrok-or-deployed-url>/webhook


Content Type

application/json


Events Selected

Push

Pull Request

Merge Group (if applicable)

ℹ️ The webhook endpoint is implemented in the separate repository: webhook-repo

🧪 How to Test

You can trigger webhook events by performing the following actions in this repository:

Push Event

Make a commit and push to any branch

Pull Request Event

Create a pull request from one branch to another

Merge Event

Merge a pull request into the target branch

Each action will automatically send a webhook payload to the configured endpoint.

🗂 Repository Role in the System
action-repo
   |
   |  (GitHub Webhook Events)
   ↓
webhook-repo (Flask + MongoDB + UI)


This repository exists only to emit events.
All processing, storage, and display logic lives elsewhere — as it should, for the sake of separation of concerns and everyone’s sanity.

🔗 Related Repository

webhook-repo – Flask webhook receiver, MongoDB storage, and UI
(Link to be provided during submission)

👩‍💻 Author

Mollika Das
B.Tech CSE | Aspiring Software / ML Engineer
