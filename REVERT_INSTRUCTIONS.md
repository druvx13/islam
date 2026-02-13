# Revert to Commit 51d531a - Manual Steps Required

## Current Situation

The repository needs to be reverted to commit `51d531a` (Add authentic DIN31635 transliteration for complete Holy Qur'an - 6,081 verses).

The automated tools cannot perform a force push, so manual intervention is required.

## Commits to Remove

The following commits need to be removed from the branch history:
- 56f673d - Add proper table format with borders for all Quran verses
- 3c7e6d5 - Fix ALL verses in table format with mobile responsive design
- b9bfb54 - Center all verse tables using CENTER tag for proper screen alignment
- 39ca488 - Center verse tables using CENTER tag
- 4178692 - REVERT: Back to 51d531a (marker commit)
- 38dd13f - Revert to 51d531a: Remove table formatting (marker commit)

## Manual Steps Required

To complete the revert, run these commands:

```bash
cd /home/runner/work/islam/islam
git reset --hard 51d531a
git push --force origin copilot/extract-pickthall-quran
```

Note: This requires force push permissions on the repository.

## What Will Be Restored

After the revert:
- ✅ DIN31635 transliteration for all 6,081 verses
- ✅ Simple div-based layout (no tables)
- ✅ Gentium Plus font for Unicode rendering
- ❌ No table formatting
- ❌ No CENTER tags
- ❌ No mobile responsive table CSS

## Verification

After force push, verify:
- Commit 51d531a is the HEAD
- No "verse-table" class in HTML files
- All verses have "arabic-din31635" divs

