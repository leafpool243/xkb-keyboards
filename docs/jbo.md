- [Description](#Description)
  - [Zbalermorna](#Zbalermorna)
- [Instructions](#Instructions)

# Description
[This file](https://github.com/leafpool243/xkb-keyboards/blob/main/jbo) contains layouts for the following:
- Zbalermorna layout

## Zbalermorna
[Zbalermorna](https://jackhumbert.github.io/zbalermorna/) is a diacritic orthography for the [Lojban](https://lojban.org) language.
All Zbalermorna letters are located where their standard U.S. QWERTY counterparts are with the following exceptions:
- Letters:
  - `'` (*y’y.bu*) is typable by striking the `h` key.
  - The diphthongs `ei`, `oi`, `ai`, and `au` are typable by striking the `[`, `]`, `;`, and `'` keys respectively.
  - The semivowels for `ĭ` and `ŭ` are typable by striking the `q` and `w` keys respectively.
  - All full vowels (including diphthongs) for *cmevla* are typable by striking the `Shift`+`[vowel]` keys.
- Other:
  - The *smaji bu* (silence mark) is typable by striking the `/` key.
  - The *tcena bu* (stretch mark) is typable by striking the `-` key.
  - The *bahe bu* (emphasis mark) is typable by striking the `,` key.  Striking it multiple times will add more dots (limit of 3).
  - The rising, falling, rising–falling, falling–rising intonation marks are typable by striking the `=`, `\`, `+` (`Shift`+`=`), and `|` (`Shift`+`\`) keys respectively.
  

# Instructions
1. Download a Zbalermorna [font](https://github.com/jackhumbert/zbalermorna/tree/master/fonts/).

2. Download [jbo](https://github.com/leafpool243/xkb-keyboards/blob/main/jbo) to `/usr/share/X11/xkb/symbols/` with the filename `jbo`.

3. Make a backup of the files `/usr/share/X11/xkb/rules/base.xml` and `/usr/share/X11/xkb/rules/evdev.xml`.  This is just in case you decide to remove the layouts or if you messed up.

4. Paste the following snipped to both `/usr/share/X11/xkb/rules/base.xml` and `/usr/share/X11/xkb/rules/evdev.xml` under `<layoutList>` (approx ln. 1344).
```xml
    <layout>
      <configItem>
        <name>jbo</name>
        <!-- Keyboard indicator for Lojban layouts -->
        <shortDescription>jbo</shortDescription>
        <description>la .lojban. (zbalermorna)</description>
        <countryList>
          <iso3166Id>JBO</iso3166Id>
        </countryList>
        <languageList>
          <iso639Id>jbo</iso639Id>
        </languageList>
      </configItem>
    </layout>
```

5. Log out and log back in.  You should then be able to find the layouts in your keyboard settings.  *It is possible that you may have to step (4) whenever you update your system.*  Please be aware of this!  If this does happen, you may want take the chance to update the backups of `base.xml` and `evdev.xml` as well.
