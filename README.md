# Epstein Estate Documents

## Important

This repository makes use of [git-lfs](https://git-lfs.com), which you should have installed before cloning.

## Status

Up-to-date as of 2025-11-12 "Seventh Production"

## What is this, anyway?

This archive has been post-processed for easier use by researchers, journalists, and other interested parties. Additional LLM-specific processing is on the way to support folks using LLMs to "chat with" the corpus.

Current differences between this release and the official US House of Representatives release:

- Opticon and Concordance databases have been rolled up to [HOUSE_OVERSIGHT_009_REPORT.csv](HOUSE_OVERSIGHT_009_REPORT.csv), collapsing multi-page documents into a single row. Note: "official" Concordance index did NOT include all metadata fields, like e-mail addresses
- All multi-page documents, in both their image and (poorly) OCR'd text forms, have been collapsed down to single files for each (see the [Merged Documents](/Merged%20Documents/) directory)
- Text files that came from iMessage have been transformed to a more readable format (see the [iMessage Transcripts](/iMessage%20Transcripts) directory)

## Still to come:

- [ ] Finish a more robust (but MUCH slower) OCR pipeline on the emails. This pipeline uses computer vision to segment headers, quoted replies, forwarded messages, etc.; it also extracts values from those headers to create _real_ metadata for organization/searching.
- [ ] Proper and useful filenames
- [ ] Update the Opticon load file with the new filenames, keeping new per-page exports alongside the full-doc merges I've already made, so it will still load into Octicon-compatible DMSs (Relativity, Concordance, etc.)
- [ ] Update the Concordance DAT file with actually useful and more rich metadata, which should load properly into Concordance, Summation, Relativity, etc.
- [ ] Create index files for easier navigation directly from Github or your own web app
- [ ] Produce LLM-friendly transforms of every file