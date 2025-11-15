# Epstein Estate Documents

## Important

This repository makes use of [git-lfs](https://git-lfs.com), which you should have installed before cloning.

## Status

- First pass is up-to-date as of 2025-11-12 "Seventh Production"
- Now working on structured data extracts from the 2,112 emails. It'll be slow-going as I'm hitting rate limits. If anyone cares to donate ($spdustin on cashapp, @spdustin on venmo) funds will go towards increasing subscription tiers. Anyone with ChatGPT, Claude, or Gemini **API** credits to comp, you can reach me on Signal (spdustin.94).

## What is this, anyway?

This archive has been post-processed for easier use by researchers, journalists, and other interested parties. Additional LLM-specific processing is on the way to support folks using LLMs to "chat with" the corpus.

Current differences between this release and the official US House of Representatives release:

- Opticon and Concordance databases have been rolled up to [HOUSE_OVERSIGHT_009_REPORT.csv](HOUSE_OVERSIGHT_009_REPORT.csv), collapsing multi-page documents into a single row. Note: "official" Concordance index did NOT include all metadata fields, like e-mail addresses
- All multi-page documents, in both their image and (poorly) OCR'd text forms, have been collapsed down to single files for each (see the [Merged Documents](/Merged%20Documents/) directory)
- Text files that came from iMessage have been transformed to a more readable format (see the [iMessage Transcripts](/iMessage%20Transcripts) directory)

## Still to come:

- [ ] ~~Finish a more robust (but MUCH slower) OCR pipeline on the emails. This pipeline uses computer vision to segment headers, quoted replies, forwarded messages, etc.; it also extracts values from those headers to create _real_ metadata for organization/searching.~~
- [ ] Finish a more robust (but MUCH slower) OCR pipeline on the emails. There is so much variation between email screenshots that fine-tuning existing models was taking too long for a volunteer project. LLM+Vision models, on the other hand, get the job done with minimal oversight. I say minimal oversight, and by that I mean I had to write six different scripts to check for stupid stuff even if the JSON files validated to the schema. _Sigh._ And I'm rapidly running out of API quota, so I'm bouncing between different vision-capable LLMs which each need their own very specific multi-stage prompting pipeline to create the output. But honestly, still better than training to label a bunch of email screenshots and train Detectron2 how to identify all the different ways the content is presented in the House's document dump.
- [ ] Proper and useful filenames
- [ ] Update the Opticon load file with the new filenames, keeping new per-page exports alongside the full-doc merges I've already made, so it will still load into Octicon-compatible DMSs (Relativity, Concordance, etc.)
- [ ] Update the Concordance DAT file with actually useful and more rich metadata, which should load properly into Concordance, Summation, Relativity, etc.
- [ ] Create index files for easier navigation directly from Github or your own web app
- [ ] Produce LLM-friendly transforms of every file