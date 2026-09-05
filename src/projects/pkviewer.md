---
order: 900
label: pkviewer
---

pkviewer turns a [*PluralKit*](https://pluralkit.me) system into a website.

PluralKit holds the identity and the data. pkviewer decides how that identity is presented on the web: every system gets a public page, every member can have one, and systems that sign in can choose a readable address and change how their pages look.

!!!warning
pkviewer is a third-party project. It is not PluralKit, and is not affiliated with or endorsed by the PluralKit project. It reads PluralKit's public API and shows only information PluralKit already makes public.
!!!

pkviewer is in **beta**. The feature set is deliberately small, and things will change.

### Addresses

Every system is reachable by its PluralKit ID from the moment it is claimed:

```
/s/abcdef
```

Once a system chooses an address, that becomes the friendlier link. Both keep working, and the chosen one is canonical:

```
/s/your-system
/s/your-system/a-member
```

A chosen address is never required for a page to be public. It only makes the link nicer to share.

### What is public

Only what PluralKit already makes public. A member you keep private in PluralKit does not appear on pkviewer, and pkviewer gives no way to tell that a private member exists at all.

You can hide public information on pkviewer if you would rather not show it — pronouns and birthdays, for example. Hiding removes the value from the page entirely, rather than tucking it out of sight.

### Signing in

Signing in uses Discord, and only to confirm who you are. pkviewer asks Discord for your account ID and username, nothing else: not your servers, not your messages, not your email.

You never have to hand pkviewer a PluralKit token to claim a system. See [*Claiming a system*](/projects/pkviewer/claiming).

### Pages

- [*Claiming a system*](/projects/pkviewer/claiming)
- [*Your public address*](/projects/pkviewer/addresses)
- [*Appearance and layout*](/projects/pkviewer/appearance)
- [*Privacy*](/projects/pkviewer/privacy)
