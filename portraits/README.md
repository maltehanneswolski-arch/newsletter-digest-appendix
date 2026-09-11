# Portraits for the digest flashcards

Person flashcards in the daily mail show a portrait when one is on file and the
person's initials when one is not. The renderer never guesses a portrait URL: a
named official beside the wrong face is a serious error, and nothing in the
editor sandbox can verify who is in a photograph.

This directory is a place to put portraits you have checked yourself. Files here
are served by `raw.githubusercontent.com` with a real `image/png` (or
`image/jpeg`) content type, verified 2026-09-11, so they hotlink from the email
without depending on a publisher's CDN or its hotlink policy.

## Adding one

1. Drop the image in here, named after the person: `kaja-kallas.jpg`.
   Square, at least 240x240. Anything smaller looks soft at 2x.
2. Commit and push to `main`.
3. In the private repo, set the person's `portrait` in `config/flashcards.json`
   to the raw URL, and `portrait_credit` to the photographer or source:

   ```json
   {
     "name": "Kaja Kallas",
     "portrait": "https://raw.githubusercontent.com/maltehanneswolski-arch/newsletter-digest-appendix/main/portraits/kaja-kallas.jpg",
     "portrait_credit": "European Union, 2024"
   }
   ```

Pushing `config/flashcards.json` does not send a digest — only
`config/manual-digest.json` does — so the card can be checked with
`./scripts/dry-render.sh` before it ever reaches an inbox.

## Licensing

Only add images you have the right to redistribute: this repository is public
and the mail hotlinks from it. Credit goes in `portrait_credit`, which renders
under the name.
