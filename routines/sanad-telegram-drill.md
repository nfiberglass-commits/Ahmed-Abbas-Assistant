# Sanad — Daily Telegram Drill (1 minute)

Replaces the long 9 p.m. Sanad coach email (Ahmed, 30 Sep 2026: "no time — make it interactive on Telegram").
The 9 p.m. routine trig_012sH95aq8NqKtkZaoen2f5b is now DISABLED (kept, not deleted).

## Flow
1. n8n workflow `jvlo3m1jkfone8Dk` — Sat–Thu 12:45 Cairo:
   whatsapp_inbox sheet → Ahmed's own messages (direction=out) from the last 36h, ≥20 chars, no media
   → Claude (claude-sonnet-5-5) picks the one that most needs improving
   → Telegram message starting "🎯 Sanad" with the original quote + the weakness + "Reply and rewrite in one line: who + what + by when".
2. Ahmed taps **Reply** and rewrites it.
3. n8n workflow `FWW8REhWxxLtNe7I` (Telegram GPT-5 mini Assistant) now passes `reply_to_message` into the agent.
   New SPECIAL RULE: a reply to a "🎯 Sanad" message gets ⭐ score /10, one thing done well, a better one-line version, one tip.
   Replies are also saved to data table ni_telegram_inbox (existing behaviour), so Coach Layla can see them weekly.

## Test
30 Sep 2026 07:56 Cairo — drill sent (Telegram message_id 42) about a message to Atef on cancelled mix orders.

## Coach Layla on Telegram (30 Sep 2026)
Coach Layla weekly (trig_01PQSojWPTtBhLue37itaUxy, Thu 9 p.m. Cairo) now sends only 3 lines to Telegram — see coach-layla-weekly-v6.md.
Delivery: row in data table telegram_outbox (KlWVqsPNNibKlgoa) → n8n workflow r0oXGGbxzgfuMKR0 "NI — Telegram Outbox to Ahmed" (manual trigger, no public endpoint) sends the newest row.
Tested 30 Sep 2026 08:50 Cairo with a setup message — execution 39869 success.
