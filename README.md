# GamesNook

A growing toolbox of party-game helpers for FFXIV hosts. Today it ships a full **blackjack dealer's table**; bingo, truth or dare, and more are planned. Open `/gnook` to start.

## Blackjack

GamesNook runs the table so you can focus on hosting. It reads real `/dice` rolls out of chat, tracks every hand and balance, and handles the bookkeeping — bets, banks, tips, payouts, and history — while you deal.

### What it does

- **Dice-driven cards.** Cards come from real `/dice 13` rolls (visible to the party, provably fair). It maps each roll to a rank, assigns a suit, and enforces a real 52-card deck that reshuffles each hand. Press **Deal** and it rolls for you.
- **Full game flow.** Per-hand Deal / Double / Split / Stand, dealer auto-play guidance, blackjack and bust detection, and **guided dealing** that highlights whose turn is next in sequence.
- **Configurable house rules.** Dealer hits/stands on soft 17, blackjack payout (3:2, 6:5, 1:1, or custom), and pool-vs-personal payout routing. Defaults to the Elysium ruleset.
- **Banking & money tracking.** Per-player banks with buy-in / cash-out, a house pool, the host's personal gil, and a tips tally — each tracked separately, with per-round and per-session profit/loss.
- **Bet locking.** Set a bet, lock it in, and it's read-only for the round; dealing is gated until it's locked.
- **Automatic trade detection.** When a player trades you gil, GamesNook detects the amount and who sent it, creates their seat if needed, and prompts you to route it to a **Bet**, **Bank**, or **Tip**.
- **Announcements & emotes.** Fully customizable per-event messages (draw, blackjack, bust, dealer draw/bust) with `{card} {player} {total} {article}` placeholders, picked at random, plus optional emote reactions.
- **Hand history.** Every settled round is logged (cards, outcomes, payouts, house net) with copy-to-clipboard export.
- **Undo.** Take back a misdealt card, or fully reverse a settle (balances, pool, and history restored).
- **Party-list integration.** Right-click a party member to add them to the table.

### Running a game

1. Type `/gnook` to open the table.
2. Set your **House pool** (and Buy-in your bankroll) on the House Bank card.
3. Flip the **Dealing** toggle on — this activates dice and trade detection, and snapshots your personal gil.
4. Add seats: right-click party members, or use **+ Add Seat**.
5. Set each player's **bet** and hit **Lock**.
6. Deal the round — the next **Deal** button glows green in sequence. Use Double / Split / Stand as players decide.
7. Play the dealer's hand (the instruction line tells you hit or stand), then **Settle Round**.
8. Payouts land in banks and the pool automatically; non-banking players are shown what to pay by trade.
9. **Next Round** when ready. Flip **Dealing** off when you're done so the plugin stops reacting to your rolls and trades.

### Settings

Open settings from the **gear icon** in the title bar (or the plugin's config button):

- **House Rules** — soft-17 behavior, pool-vs-personal payout.
- **Blackjack Payout** — the payout ratio.
- **Dealing** — guided dealing, trade detection, and a debug mode that accepts rolls in any channel for solo practice.
- **Announcements / Emote Reactions** — customize what the plugin says and does on each event.

## Notes & limitations

- **Automation:** GamesNook sends `/dice`, party messages, and (optionally) emotes on your behalf when you press its buttons. This is third-party automation; use it knowingly and at your own discretion.
- **English client:** dice-roll and trade detection rely on English chat text. On non-English clients, roll and trade detection won't fire (the rest of the tool still works if you enter values manually).
- The plugin does the math and tells you what to trade — it never moves gil on its own.

## Installation

1. Open XIVLauncher settings.
2. Go to **Dalamud** → **Custom Plugin Repositories**.
3. Add:
   ```
   https://github.com/devoreofox/GamesNook/raw/refs/heads/main/repo.json
   ```
4. Open `/xlplugins` in-game and search for **GamesNook**.

## License

AGPL-3.0-or-later

## Attribution

GamesNook is free software under the AGPL-3.0, and attribution is required. If you fork it, redistribute it, or reuse its code, you must keep the existing copyright and license notices in place and credit the original author (Oreo) with a visible link back to this repository (https://github.com/devoreofox/GamesNook). Please do not remove or hide that attribution.
