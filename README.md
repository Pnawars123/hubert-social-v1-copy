# Hubert Social v1 — launch notification copy

Notification copy for the Hubert Social v1 launch nudge, in two A/B variants, across all 21
locales. This is a standalone home for the copy for a project — it is **not** wired into any
pipeline; nothing here renders on its own.

## What's here

- `content/locales/<locale>/notifications.json` — one file per locale, laid out the way
  team.blue's config-store stores notification copy (flat keys, not wrapped).
- `hubert-social-v1-all-locales.json` — the same content as one combined file, for convenience.

Two notification keys, each with a title, two body lines (`subtitles`), a primary and secondary
CTA, and `ctaAction: hubert`:

- `HG-SM-notification-hubert-social-v1-a` — the "social media is like working out daily" angle
- `HG-SM-notification-hubert-social-v1-b` — the shorter "what if the writing took care of
  itself" angle

## Locales

All 21 carry full, real copy: en, it, fr, es, de, de-CH, nl, nl-BE, pt, el, bg, ca, cs, da, fi,
hu, no, sk, sr, sv, tr.

## Corrections made to the source file

The uploaded draft had three issues, fixed here:

1. **Structure.** The source wrapped every locale in an extra `{ "notifications": { … } }`
   layer. config-store stores these flat — keys at the top level — so this version is flattened
   to match.
2. **Keys.** The source used `hubert-social-v1-a` / `-b`. These now follow the
   `HG-SM-notification-*` prefix that the rest of the family uses (per TB-789), so they'd drop
   into config-store without the silent-fallback problem an off-prefix id causes.
3. **Translations.** 11 of the 21 locales (bg, ca, cs, da, fi, hu, no, sk, sr, sv, tr) were
   pasted in as English with only the secondary button translated. Those now carry full, real
   translations for the title and both body lines, same as the other 10.

`ctaAction: hubert` was added to every entry, matching how the rest of the SimplyBook /
Hubert notification family is shaped.

## Before this ships anywhere real

- The keys here are proposals that fit the mandated prefix, not confirmed ids — TB-789 owns
  `FAMILY_NOTIFICATION_IDS` and assigns the actual id.
- The 11 newly-translated locales are worth a native-speaker pass before going live, same as
  any first full translation.
