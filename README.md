**English** · [Français](README.fr.md)

**Anthony Hunt** · [Project page on ingevision.cloud](https://ingevision.cloud/en/ai-agents/?p=agent-equipe-de-nuit) · [LinkedIn](https://www.linkedin.com/in/anthony-hunt-3948a9196) · [GitHub profile](https://github.com/anthohunt)

> Showcase repository: the code and data of this project are private; this README describes it.

# Agent - Website night shift

Five agents that look after a personal website every night, one after the other: quality, performance, security, and two that look for the people who could use it. In the morning, one short email sums up what they fixed and what is left for the owner to decide.

## The problem

A one-person website drifts quietly: a link breaks, a project page stops matching its repository, a page gets heavier, a security header goes missing, the English version lags behind the French one. Checking all of that by hand every week is exactly the kind of chore that never gets done.

## How it works

- **One agent per night slot**, on a home workstation: clients at midnight, recruiting at 1 am, quality at 2 am, performance at 3 am, security at 4 am. Each one has its own written mission and its own memory of past nights.
- **Quality** replays every user story of the site's design mock-up in a real browser, desktop and phone, opens every project page in both languages and checks each one against its GitHub repository.
- **Performance** measures page weight and speed and keeps the figures night after night: a number that gets worse is a fault even if it is still "fine".
- **Security** checks headers, certificates, dependencies and that no personal data leaks into public pages or repositories.
- **Clients and recruiting** only prepare: who might be interested and what could be published. They contact nobody.
- **What an agent may do alone**: factual, mechanical fixes (a broken link, a wrong "Live: No", a missing header). It publishes, checks the result online on desktop and phone, and commits with the reason. A fix it cannot see working online is rolled back.
- **What it only proposes**: wording, design, anything that is the owner's choice. The morning email lists these with an ID; replying "yes ID" or "no ID" is the whole review.
- **Effort is counted, not declared**: a script reads each agent's session afterwards (actions really taken, pages opened, user stories cited, repositories checked). Below the floor, the agent is sent back to finish what is missing.

## What is built

In service since 9 November 2026. First night: 142 page views checked with no JavaScript error, 46 of 47 user stories conforming after one fix, 30 project pages checked in both languages, 3 fixes published (phone back button, sitemap, a wrong "Live" field); HTTPS enforced and a content security policy added; fonts served by the site itself instead of a third party.

## What is public

This page only. The missions, memories and reports describe a private setup.

## Tech stack

- Claude Code agents, run headless on a schedule
- Playwright (real browser, desktop and phone)
- Python (effort counter, morning email, reading the replies)
- nginx, git
