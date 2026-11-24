# BarKap word list

`words.json` is the word content of the BarKap (ԲառԿապ) app. The app downloads it in
the background and uses it **from the next app start**.

## Editing

1. Edit `words.json` (one group or family per line).
2. **Increase `version` by 1.** Apps only take a file whose `version` is higher than the
   one they have, so an edit without a new version is never picked up.
3. Leave `schema` at `1`. It changes only if the file format changes; apps ignore
   formats they don't know.

The app rejects the whole file (and keeps its current words) if anything is wrong:

- every word must be unique across all groups (case-insensitive) and at most 14 letters;
- every group needs an `id` without `:`, a `name` and at least 5 words;
- there must be at least 25 groups;
- every family needs at least 5 member groups, each existing and listed in `symbols`.

A word written as `["խնձոր", "food-apple"]` can appear as a picture card. The icon is
a [Material Community Icons](https://pictogrammers.com/library/mdi/) name; an unknown
name only drops the picture, the word stays.

When the board's words change, players who are in the middle of a level get a newly
dealt board at the same level number.
