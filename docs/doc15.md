# Slack: #ci-cd - 2025-08-18 - Flaky test in user-service pipeline

## Content
- **User A:** "The `user-service` build is failing intermittently on the `TestUserLogin` integration test. Anyone know why?"
- **User B:** "I've seen that one. It's a race condition. The test tries to fetch a user record before the database transaction has committed."
- **User A:** "Ugh. Is there a quick fix?"
- **User B:** "Not a clean one. You can add a `sleep(1)` to the test, but the right way is to rewrite it to be less dependent on timing."