# 01_02 — Why Software Testing is Important — and What to Test

## Why testing is important

- **For individual users (B2C):** the market has thousands of options ("100,500"). In a market like that, the products that win are the ones that work well for users — testing protects that.
- **For enterprises (B2B):** they count money and risks. Quality affects those calculations — a failure can cost millions.
- **For everyone (life-critical):** trains, planes, ships, nuclear plants, medical equipment. "Smartphone failure is bad, but an airplane crash is incomparably worse." Real cases: Therac-25, Boeing 737 MAX.

## What to test — the four areas

1. **Software** — the running product (classic testing).
2. **Code** — reviews, static analysis (no need to run it).
3. **Prototype** — early versions; problems found here are much cheaper to fix.
4. **Documentation** — manuals and guides have bugs too.

Big idea: "we can test **literally everything**" — and the earlier you test, the cheaper the fix.

## The tricky part (B2C vs B2B)

- **B2C** = Business to **Consumer** → products for individual people (Netflix, a mobile game).
- **B2B** = Business to **Business** → products for companies (Jira, a bank's payment system).

Individual users buy with emotion (and fall for **hype**); enterprises buy with calculations (money and **risks**).

## Example

A bank: one hour of **downtime** in the payment system = millions lost. That is why enterprise clients ask hard questions about quality — and testing is the evidence.
