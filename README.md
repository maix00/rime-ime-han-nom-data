# Han-Nom Telex for Rime

A Vietnamese Han-Nom Telex schema and dictionary for Rime, adapted from the upstream [rime-ime-han-nom-data](https://github.com/miketvo/rime-ime-han-nom-data) project.

This fork carries local improvements to Telex spelling, case handling, live Vietnamese preedit, punctuation, mixed Han-Nom/Vietnamese composition, and dictionary coverage. It is an independent community fork and is not an official Rime or Han-Nom Revival Committee release.

## Install

Use a Rime distribution with Lua support enabled. Copy these files into the Rime user-data directory, keeping the `lua/` subdirectory:

- `hannom-telex.schema.yaml`
- `hannom-telex.dict.yaml`
- `lua/hannom_telex_enter.lua`
- `lua/hannom_telex_segmentor.lua`
- `lua/hannom_telex_preview.lua`
- `lua/hannom_telex_preedit_filter.lua`
- `lua/hannom-telex-syllables.tsv`

Common user-data locations are `~/Library/Rime` for Squirrel on macOS and `%APPDATA%\Rime` for Weasel on Windows. Add `hannom-telex` to the existing `schema_list` in `default.custom.yaml`, then redeploy Rime. Merge the schema entry with your existing list so your other input methods stay enabled.

```yaml
patch:
  schema_list:
    - schema: hannom-telex
```

The schema depends on Rime's `cangjie5` schema for reverse lookup.

## What this fork changes

- Keeps the full unconfirmed Telex input available to dictionary and phrase lookup while showing Vietnamese syllable boundaries in the preedit.
- Converts valid Telex to Vietnamese on Return and supports mixed selected Han-Nom and unselected Vietnamese text.
- Supports upper-case Telex lookup and preserves case in Vietnamese output.
- Handles tone-key placement variants, `dd`/`Đ`, half-width punctuation, and spacing around punctuation.
- Expands Han-Nom dictionary coverage with additional entries from documented sources.

The project is under active revision. The schema was built with Squirrel on macOS during development; key-by-key behavior and other Rime distributions have not been freshly verified for this release.

## Data sources and acknowledgements

This fork preserves the upstream project history and MIT license. The original schema and dictionary work is by Mike Vo (武祥明), building on Weasel Hannom by Keepout2010. Dictionary sources documented upstream and in the data include:

- [Chữ Nôm Standard](https://chunom.org/pages/standard/)
- [Vietnamese Wiktionary](https://vi.wiktionary.org/)
- [HVDic](https://hvdic.thivien.net/rad-hv)
- [Han-Nom Revival Committee standard lookup](https://www.hannom-rcv.org/standard-nom/Lookup-CHNC.html)

See [LICENSE](LICENSE) and the upstream repository for attribution and source history.

## License

MIT. The upstream copyright and license notice are retained in [LICENSE](LICENSE).
