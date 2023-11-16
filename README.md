# xkb-keyboards
Various XKB layouts for conlangs

- qtq (Toaq, *Tóaqzu*)
- jbo (Lojban, *lo jbobau*) — soon

## Instructions
Download one of the keyboard files (e.g. [https://github.com/leafpool243/xkb-keyboards/blob/main/qtq qtq]) to the folder `/usr/share/X11/xkb/symbols/` with the same filename it has in this repo.

Paste the corresponding xml snippet to `/usr/share/X11/xkb/rules/base.xml` **and** `/usr/share/X11/xkb/rules/evdev.xml` under `<layoutList>` (approx ln. 1344)
* **qtq**
```
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
