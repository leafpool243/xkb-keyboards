- [#Description](Description)
  - [#Latin](Latin)
  - [#Deranı](Deranı)
- [#Instructions](Instructions)

# Description
[This file](https://github.com/leafpool243/xkb-keyboards/blob/main/qtq) contains layouts for the following:
- Latin layout
- Deranı layout

## Latin
This layout follows the standard U.S. QWERTY layout with the following exceptions:
- Tones:
  - The second tone (◌́) is typable by striking the `'` key, followed by a vowel.
  - The third tone (◌̈) is typable by striking the `"` key (`Shift`+`'`), followed by a vowel.
  - The fourth tone (◌̂) is typable by striking the `;` key, followed by a vowel.
- Letters:
  - O’aomo (`’`) is typable by striking the `x` key
  - `Ꝡ` and `ꝡ` are typable by striking the `W` (`Shift`+`w`) and `w` keys respectively.
- Prefixes:
- The underdot is typable by striking the `v` key and then the vowel on which to apply the diacritic.
  - If you also need a tone diacritic, you may type both `v` `[tone]` `[vowel]` or `[tone]` `v` `[vowel]`.
 - The alternate first tone diacritic (◌̀) for the Prefix Reform is typable by striking the `V` key (`Shift`+`v`) and then the vowel on which to apply the diacritic.
- Other:
  - `«`, `»`, `‹`, and `›` are typable by striking the `[`, `]`, `{` (`Shift`+`[`), and `}` (`Shift`+`]`) keys respectively.
  - The old tone diacritics ◌̄, ◌̌, ◌̉, ◌̀, and ◌̃ are typable by striking the `X` (`Shift`+`x`), `AltGr`+`\`, `:` (`Shift`+`;`), `AltGr`+`|` (`AltGr`+`Shift`+`\`) respectively, followed by a vowel.

## Deranı
This layout mostly follows the layout of the consonants in the Latin layout. Since vowel characters are the same as consonants, those keys can be used for other purposes.
The changes are as follows:
- Tones:
  - The second tone is typable by striking the consonant followed by `e`.
  - The third tone is typable by striking the consonant followed by `u`.
  - The fourth tone is typable by striking the consonant followed by `o`.
- Letters and other symbols:
  - O’aomo is typable by striking the `a` key.
  - Coda `m` is typable by striking the `M` (`Shift`+`m`) key.
  - The diphthong mark is typable by striking the `y` key.
  - The hiatus mark is typable by striking the `;` key.
  - The null variable mark is typable by striking the `:` (`Shift`+`;`) key.
  - The cartouche start and cartouche end characters are typable by striking the `'` and `"` (`Shift`+`"`) keys respectively.
  - The subordination mark, declarative full stop, and non-declarative full stop are typable by striking the `,`, `.`, and `/` keys respectively.
  - The prefix mark, quotation mark, and question mark are typable by striking the `<` (`Shift`+`,`), `>` (`Shift`+`.`), and `?` (`Shift`+`/`) keys respectively.

# Instructions
1. Download [qtq](https://github.com/leafpool243/xkb-keyboards/blob/main/qtq) to `/usr/share/X11/xkb/symbols/` with the filename `qtq`.

2. Make a backup of the files `/usr/share/X11/xkb/rules/base.xml` and `/usr/share/X11/xkb/rules/evdev.xml`.  This is just in case you decide to remove the layouts or if you messed up.

3. Paste the following snipped to both `/usr/share/X11/xkb/rules/base.xml` and `/usr/share/X11/xkb/rules/evdev.xml` under `<layoutList>` (approx ln. 1344).
```xml
<layout>
  <configItem>
    <name>qtq</name>
    <shortDescription>qtq</shortDescription>
    <description>Toaqzu (Hoegua, Latınalaı)</description>
    <countryList>
      <iso3166Id>QTQ</iso3166Id>
    </countryList>
    <languageList>
      <iso639Id>qtq</iso639Id>
    </languageList>
  </configItem>
  <variantList>
    <variant>
      <configItem>
        <name>derani</name>
        <description>Toaqzu (Hoegua, Deranı)</description>
      </configItem>
    </variant>
  </variantList>
</layout>
```
4. Add the following to ~/.XCompose.  If you already have `include "%L"` in your `.XCompose` file, you do *not* need it twice.

```
include "%L"

# Dotless ı + tone
<dead_acute> <idotless>                 	: "í"   iacute # LATIN SMALL LETTER I WITH ACUTE
<dead_diaeresis> <idotless>             	: "ï"   idiaeresis # LATIN SMALL LETTER I WITH DIAERESIS
<dead_hook> <idotless>                  	: "ỉ"   U1EC9 # LATIN SMALL LETTER I WITH HOOK ABOVE
<dead_circumflex> <idotless>            	: "î"   icircumflex # LATIN SMALL LETTER I WITH CIRCUMFLEX
<dead_grave> <idotless>                 	: "ì"   igrave # LATIN SMALL LETTER I WITH GRAVE
<dead_tilde> <idotless>                 	: "ĩ"   U0129 # LATIN SMALL LETTER I WITH TILDE
<dead_caron> <idotless>                 	: "ǐ"   U01D0 # LATIN SMALL LETTER I WITH CARON
<dead_macron> <idotless>                	: "ī"   U012B # LATIN SMALL LETTER I WITH MACRON

# underdots + tone (DELTA)
<dead_acute> <dead_belowdot> <a>             :"ạ́"
<dead_diaeresis> <dead_belowdot> <a>         :"ạ̈"
<dead_circumflex> <dead_belowdot> <a>        :"ậ"
<dead_acute> <dead_belowdot> <e>             :"ẹ́"
<dead_diaeresis> <dead_belowdot> <e>         :"ẹ̈"
<dead_circumflex> <dead_belowdot> <e>        :"ệ"
<dead_acute> <dead_belowdot> <idotless>      :"ị́"
<dead_diaeresis> <dead_belowdot> <idotless>  :"ị̈"
<dead_circumflex> <dead_belowdot> <idotless> :"ị̂"
<dead_acute> <dead_belowdot> <o>             :"ọ́"
<dead_diaeresis> <dead_belowdot> <o>         :"ọ̈"
<dead_circumflex> <dead_belowdot> <o>        :"ộ"
<dead_acute> <dead_belowdot> <u>             :"ụ́"
<dead_diaeresis> <dead_belowdot> <u>         :"ụ̈"
<dead_circumflex> <dead_belowdot> <u>        :"ụ̂"
<dead_belowdot> <dead_acute> <a>             :"ạ́"
<dead_belowdot> <dead_diaeresis> <a>         :"ạ̈"
<dead_belowdot> <dead_circumflex> <a>        :"ậ"
<dead_belowdot> <dead_acute> <e>             :"ẹ́"
<dead_belowdot> <dead_diaeresis> <e>         :"ẹ̈"
<dead_belowdot> <dead_circumflex> <e>        :"ệ"
<dead_belowdot> <dead_acute> <idotless>      :"ị́"
<dead_belowdot> <dead_diaeresis> <idotless>  :"ị̈"
<dead_belowdot> <dead_circumflex> <idotless> :"ị̂"
<dead_belowdot> <dead_acute> <o>             :"ọ́"
<dead_belowdot> <dead_diaeresis> <o>         :"ọ̈"
<dead_belowdot> <dead_circumflex> <o>        :"ộ"
<dead_belowdot> <dead_acute> <u>             :"ụ́"
<dead_belowdot> <dead_diaeresis> <u>         :"ụ̈"
<dead_belowdot> <dead_circumflex> <u>        :"ụ̂"
<dead_acute> <dead_belowdot> <A>             :"Ạ́"
<dead_diaeresis> <dead_belowdot> <A>         :"Ạ̈"
<dead_circumflex> <dead_belowdot> <A>        :"Ậ"
<dead_acute> <dead_belowdot> <E>             :"Ẹ́"
<dead_diaeresis> <dead_belowdot> <E>         :"Ẹ̈"
<dead_circumflex> <dead_belowdot> <E>        :"Ệ"
<dead_acute> <dead_belowdot> <I>             :"Ị́"
<dead_diaeresis> <dead_belowdot> <I>         :"Ị̈"
<dead_circumflex> <dead_belowdot> <I>        :"Ị̂"
<dead_acute> <dead_belowdot> <O>             :"Ọ́"
<dead_diaeresis> <dead_belowdot> <O>         :"Ọ̈"
<dead_circumflex> <dead_belowdot> <O>        :"Ộ"
<dead_acute> <dead_belowdot> <U>             :"Ụ́"
<dead_diaeresis> <dead_belowdot> <U>         :"Ụ̈"
<dead_circumflex> <dead_belowdot> <U>        :"Ụ̂"
<dead_belowdot> <dead_acute> <A>             :"Ạ́"
<dead_belowdot> <dead_diaeresis> <A>         :"Ạ̈"
<dead_belowdot> <dead_circumflex> <A>        :"Ậ"
<dead_belowdot> <dead_acute> <E>             :"Ẹ́"
<dead_belowdot> <dead_diaeresis> <E>         :"Ẹ̈"
<dead_belowdot> <dead_circumflex> <E>        :"Ệ"
<dead_belowdot> <dead_acute> <I>             :"Ị́"
<dead_belowdot> <dead_diaeresis> <I>         :"Ị̈"
<dead_belowdot> <dead_circumflex> <I>        :"Ị̂"
<dead_belowdot> <dead_acute> <O>             :"Ọ́"
<dead_belowdot> <dead_diaeresis> <O>         :"Ọ̈"
<dead_belowdot> <dead_circumflex> <O>        :"Ộ"
<dead_belowdot> <dead_acute> <U>             :"Ụ́"
<dead_belowdot> <dead_diaeresis> <U>         :"Ụ̈"
<dead_belowdot> <dead_circumflex> <U>        :"Ụ̂"
```

5. Log out and log back in.  You should then be able to find the layouts in your keyboard settings.  *It is possible that you may have to step (3) whenever you update your system.*  Please be aware of this!  If this does happen, you may want take the chance to update the backups of `base.xml` and `evdev.xml` as well.
