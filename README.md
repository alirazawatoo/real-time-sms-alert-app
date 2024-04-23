# Real-Time SMS Alert App

A Rails/Twilio demonstration for queueing SMS delivery, receiving provider status webhooks, and broadcasting status changes through Action Cable.

```text
user action -> Sidekiq send job -> Twilio SMS
                                  -> status webhook -> message update -> live notification
```

Configure PostgreSQL, Redis, Twilio credentials, a sending number, and a public callback URL, then run `bundle install`, database setup, Sidekiq, and `./bin/dev`.

Use synthetic recipients. Webhook signature validation, idempotent transitions, consent, rate limits, and retries require production review.
