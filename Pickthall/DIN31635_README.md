# DIN31635 Transliteration for Pickthall Quran

## What is DIN31635?

DIN 31635 is the **German standard (Deutsches Institut für Normung) for Arabic transliteration**. It is designed to represent Arabic text accurately in Latin script, especially for scholarly and academic purposes.

## Key Characteristics of DIN31635

### 1. Represents RECITATION (Spoken Form)
- Shows exactly what is pronounced during Quranic recitation
- Accounts for phonetic assimilation (e.g., sun and moon letters)
- Does NOT represent silent letters or purely orthographic features

### 2. Uses Proper Unicode Diacritics
The standard uses specific Unicode characters with diacritics:

**Long Vowels:**
- ā (U+0101) - long 'a'
- ī (U+012B) - long 'i'  
- ū (U+016B) - long 'u'

**Emphatic Consonants:**
- ṣ (U+1E63) - emphatic 's' (ص)
- ḍ (U+1E0D) - emphatic 'd' (ض)
- ṭ (U+1E6D) - emphatic 't' (ط)
- ẓ (U+1E93) - emphatic 'z' (ظ)

**Pharyngeal and Glottal:**
- ḥ (U+1E25) - pharyngeal 'h' (ح)
- ḫ (U+1E2B) - velar fricative (خ)
- ʿ (U+02BF) - voiced pharyngeal fricative (ع - ain)
- ʾ (U+02BE) - glottal stop (ء - hamza)

**Other Special Characters:**
- ṯ (U+1E6F) - 'th' as in 'think' (ث)
- ḏ (U+1E0F) - 'th' as in 'this' (ذ)
- š (U+0161) - 'sh' (ش)
- ġ (U+0121) - voiced velar fricative (غ)

### 3. Clean Text Format
- NO HTML tags (<u>, <b>, etc.)
- NO custom encoding schemes
- Pure Unicode characters as per standard

## Example: Sura 1 (Al-Fatiha) in Proper DIN31635

```
1. bismillāhi r-raḥmāni r-raḥīm
2. al-ḥamdu lillāhi rabbi l-ʿālamīn
3. ar-raḥmāni r-raḥīm
4. māliki yawmi d-dīn
5. iyyāka naʿbudu wa-iyyāka nastaʿīn
6. ihdinā ṣ-ṣirāṭa l-mustaqīm
7. ṣirāṭa llaḏīna anʿamta ʿalayhim ġayri l-maġḍūbi ʿalayhim wa-lā ḍ-ḍāllīn
```

**Note the key features:**
- "bismillāhi r-raḥmāni" - shows the assimilation before 'r' (sun letter)
- "al-ḥamdu" - 'al-' before moon letter (ḥ) stays as 'al-'
- "ṣ-ṣirāṭa" - shows the assimilated article before ṣ
- Proper diacritics: ā, ī, ḥ, ʿ, ṣ, ġ, ḍ, ḏ

## What Was Wrong With Previous Implementation

The previous implementation used:
1. **Yusuf Ali's custom HTML format** (not DIN31635)
2. HTML tags like `<u>a</u>` instead of proper Unicode `ā`
3. Custom representations like "AA" for ʿ (ain)
4. Did not properly show sun letter assimilation

Example of incorrect format:
```html
Bismi All<u>a</u>hi a<b>l</b>rra<u>h</u>m<u>a</u>ni a<b>l</b>rra<u>h</u>eem<b>i</b>
```

## Requirements for Proper DIN31635 Implementation

To properly implement DIN31635 transliteration, you would need:

### 1. Accurate Data Source
A complete Quranic corpus with proper DIN31635 transliteration for all 6,236+ verses, such as:
- Tanzil.net transliteration project
- Quranic Arabic Corpus
- Manual scholarly transliteration following DIN31635 rules

### 2. Complete Unicode Support
- Ensure all characters render properly with appropriate fonts
- Gentium Plus is a good choice as it supports all required diacritics

### 3. Recitation Rules Implementation
Proper handling of:
- Sun letters (ت، ث، د، ذ، ر، ز، س، ش، ص، ض، ط، ظ، ل، ن)
- Moon letters (ا، ب، ج، ح، خ، ع، غ، ف، ق، ك، م، ه، و، ي)
- Assimilation patterns
- Pausal forms (optional)

## Current Status

The Pickthall directory currently contains:
- ✅ English translation by M.M. Pickthall
- ❌ NO transliteration (incorrect version removed)

The incorrect Yusuf Ali HTML-formatted transliteration has been removed to avoid confusion.

## Next Steps

To add proper DIN31635 transliteration:

1. **Obtain proper DIN31635 data** for all 114 suras
2. **Validate** the transliteration follows DIN31635 standard
3. **Integrate** into HTML files with proper CSS styling
4. **Test** rendering with Unicode-compliant fonts
5. **Verify** accuracy for scholarly use

## References

- DIN 31635:2011-07 - Umschrift des arabischen Alphabets für die Sprachen Arabisch, Osmanisch-Türkisch, Persisch, Kurdisch, Urdu und Paschtu
- ISO 233:1984 - Documentation — Transliteration of Arabic characters into Latin characters
- Quranic Arabic Corpus: http://corpus.quran.com/
- Tanzil Project: https://tanzil.net/

---

**Note**: Proper DIN31635 transliteration requires expert knowledge of Arabic phonology and Quranic recitation rules. It is recommended to use verified scholarly sources rather than automated conversion.
