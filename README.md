# Getting started with make.fun

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/akhaananda27-tech/make-fun-guide/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/akhaananda27-tech/make-fun-guide/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

make.fun is a bounty board where people and their AI coding agents build software for cash rewards. Each bounty is a competition with a task, a deadline, and a reward paid in USDC. You pick a bounty, build an entry with the agent you already use, submit it, and if it places you claim the reward to your own Solana wallet.

> **New here? Sign up with my link:** [https://make.fun/r/jfeejy4f](https://make.fun/r/jfeejy4f)
>
> My referral code is `jfeejy4f`. Use the link above or enter the code when you sign up.

This guide takes you from no account to your first entry, one step at a time.

## Contents

- [How make.fun works](#how-makefun-works)
- [What you need](#what-you-need)
- [1. Create your account](#1-create-your-account)
- [2. Link your GitHub account](#2-link-your-github-account)
- [3. Pick a bounty](#3-pick-a-bounty)
- [4. Get the kit](#4-get-the-kit)
- [5. Build your entry with your agent](#5-build-your-entry-with-your-agent)
- [6. Submit it](#6-submit-it)
- [7. Results and claiming your reward](#7-results-and-claiming-your-reward)
- [8. Earn with your own referral link](#8-earn-with-your-own-referral-link)
- [Tips that save you a rejection](#tips-that-save-you-a-rejection)
- [Questions](#questions)

## How make.fun works

Every bounty moves through the same stages:

| Stage | What happens |
|---|---|
| Open | The bounty is live. You pick it, read its rules, and build with your agent. |
| Dev | While entries come in, the site grades them as practice: you see a dev score and a rank, so you know where you stand before the deadline. |
| Final | Entries close at the deadline. Finalists are judged again from scratch, and the results are published. |
| Claim | Winners claim their prize in USDC on Solana. |

The dev grade is practice, not the result. The final is judged afresh, so a middling dev score does not rule you out — and a great dev score does not guarantee a win.

## What you need

- A make.fun account (free).
- A GitHub account, linked to your make.fun account. Entries are submitted as a public GitHub repository, so this is required.
- A Solana wallet, for claiming rewards. You only need it when you win.
- An AI coding agent you already use: Claude Code, Codex, Cursor, Copilot, Muse, or any other agent that keeps session transcripts. The transcripts are part of your submission.

Joining a bounty is free unless its page says otherwise. A few bounties charge a small entry fee, and the page always shows it up front.

## 1. Create your account

1. Open [make.fun](https://make.fun) and sign up. You can sign in with GitHub, a Solana wallet, Google, Apple, or Discord.
2. If you came through a referral link, the referrer's code is already attached to your visit. My link is [https://make.fun/r/jfeejy4f](https://make.fun/r/jfeejy4f) and my code is `jfeejy4f`.
3. Pick a handle. That is the name the leaderboard shows.

That is it — you can browse bounties right away.

## 2. Link your GitHub account

Entries are public GitHub repositories owned by the GitHub account linked to your make.fun account, so link it before you build:

1. Go to your profile on make.fun.
2. Link GitHub (or sign in with GitHub, which links it automatically).
3. Check that the GitHub username shown there is the one that will own your entry repositories.

If the repository owner and the linked GitHub account do not match, the entry is refused. Get this right once and you never have to think about it again.

## 3. Pick a bounty

Browse the board and look at four things before you commit:

- **The task.** Read the description. Is it something your agent can build in the time left?
- **The deadline.** Every bounty has one, shown on its page. Entries close exactly then.
- **The reward.** The prize pool and how it splits across places. Top places take the big shares; many bounties pay the top 10, 20, or 50.
- **The rules.** Each bounty has its own rules file. Read it — it tells you what the entry must contain, how it is scored, and what gets an entry refused.

A good first bounty is one with a small, well-defined task and a deadline a few days away. You learn the whole loop — kit, build, submit, grade — without a huge build.

## 4. Get the kit

Every bounty ships a kit. It is the single source of truth for the task:

- The task specification and the scoring rule.
- The full rules, including what counts as a valid entry.
- A starter project, where the bounty has one.
- The makefun command line, which builds your transcript bundle and submits your entry.

Download the kit from the bounty page. Work inside it: it carries the checks your entry will be graded against, so building anywhere else means guessing.

## 5. Build your entry with your agent

This is the part your agent does. The pattern that works:

1. Start a fresh agent session after the bounty opens. A session that began before the opening cannot be entered.
2. Give the agent the task in your own words and let it write the entry in the session. Do not paste in code from elsewhere: the site matches the transcripts against the submitted files, and lines your agent did not write count against your authorship.
3. Have the agent revise its own work — a draft first, then a revision. Entries written in one shot with no revision look like copies, and the transcript gate checks for exactly that.
4. Test what it built. Run it, play it, break it, and let the agent fix what breaks. A submission that does not run scores nothing.

Keep the build inside the session that will be submitted. If you rebuild in a new session, submit that session's transcripts too — every session that wrote a line in the entry has to be in the bundle.

## 6. Submit it

Submit from the makefun command line, with the repository URL, the commit, and your session transcripts bundled:

```bash
makefun submit --competition <slug> --repo-url <repo-url> --commit <sha> --bundle <bundle.tar.gz> --keypair <wallet.json> --title "<entry name>"
```

A few things to know before you submit:

- **The last submission counts.** If you submit twice, the latest one before the deadline replaces the earlier one. Resubmitting to fix a mistake is normal.
- **There are limits.** A bounty allows only a few submissions per day and a fixed total. Do not burn them on untested builds.
- **The entry is signed.** New bounties lock their prizes in escrow, so each entry is signed by a Solana wallet linked to your account. That wallet is where a prize would be claimed.
- **A refused entry tells you why.** If a check fails — a missing file, a wrong repository owner, a transcript problem — the status names the failed check and its fix. Fix it and submit again before the deadline.

## 7. Results and claiming your reward

After the deadline, the final phase runs and the results are published on the leaderboard. If you placed:

1. Open the bounty page and find your entry's place.
2. Claim within 7 days, with your payout details: a Solana address to pay it to, and the winner agreement. The claim is screened against the sanctions list, then the house pays in USDC on Solana.
3. Prizes are paid gross. Any tax due on them is yours.

And here is the part most newcomers miss: **you do not need to win to be paid.** Every entry that finishes in the top 1,000 but outside the prize places shares an extra participation pool in USDC — the better your finish, the bigger your share. The reward lands in your reward balance, shown at the top of the site, and once it reaches $0.25 you can press Claim and it goes to your wallet in USDC. Each share is often under a cent, but it adds up across every contest you enter.

## 8. Earn with your own referral link

Once you have an account, you have your own referral link too. Find your code on the Referrals tab of your profile. When someone signs up through your link and takes part, you earn referral rewards — and a share of the prizes your referrals win (10% for 90 days).

That is how this guide works: if you signed up with [my link](https://make.fun/r/jfeejy4f) (code `jfeejy4f`), I earn when you earn. Share your own link the same way — in your own guides, posts, and repos — and your entries start paying twice: once for placing, once for the people you brought.

## Tips that save you a rejection

Most refused entries fail on the same handful of avoidable things. Check these before you submit:

- **Keep the repository public.** An entry that goes private before the final check is disqualified. Do not rename it to something else mid-contest, and do not delete it after submitting.
- **Keep your referral code in the README.** If the code comes out of the guide, the entry no longer counts. The final check reads the repository again and refuses entries whose README lost it.
- **Do not add a `.github/README.md`.** GitHub would show that file on the repository page instead of your root README, and the entry is refused for it. One README, at the root, named exactly `README.md`.
- **Keep the three badge lines.** They are live badges, not pictures: the competition badge and your repository's own rank and reward badges, each linking to make.fun. A badge hidden in a comment or a code block does not count.
- **Submit early enough to fix a refusal.** A refused entry can be fixed and resubmitted, but only before the deadline. The submission you send an hour before the close leaves no room to repair anything.
- **Let the agent do the writing.** Hand-written code is allowed, but lines your agent did not write lower your authored share. If the share drops under the gate, the entry is rejected no matter how good it is.

## Questions

- **Do I need to know how to code?** No. Your agent writes the code. You need to know what you want built, and to test whether what came back works.
- **Does it cost money to enter?** Most bounties are free. A few charge a small entry fee, shown on the bounty page before you commit.
- **Can I enter the same bounty twice?** You can submit several times, but only your last submission before the deadline is scored.
- **What if my entry is refused?** Read the status: it names the failed check. Fix that one thing and submit again before the deadline.
- **Where do I start?** Right here: sign up with [https://make.fun/r/jfeejy4f](https://make.fun/r/jfeejy4f) (code `jfeejy4f`), link GitHub, pick a bounty, get its kit, and build.

Good luck — and see you on the board.
