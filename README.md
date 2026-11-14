# QCF V1 Madinah Quran Reader — PWA

QCF V1 page-specific font ഉപയോഗിച്ച് Quran.com API-യിൽ നിന്നുള്ള പാഠം തുടർച്ചയായി സ്ക്രോൾ ചെയ്ത് വായിക്കാനുള്ള static web app.

## GitHub Pages പ്രസിദ്ധീകരണം

1. GitHub-ൽ repository സൃഷ്ടിക്കുക.
2. ഈ ഫോൾഡറിലെ ഫയലുകൾ repository root-ലേക്ക് upload ചെയ്യുക.
3. **Settings → Pages → Deploy from a branch** തിരഞ്ഞെടുക്കുക.
4. `main` branch, `/ (root)` തിരഞ്ഞെടുക്കുക.
5. ലഭിക്കുന്ന HTTPS URL തുറക്കുക.

## നിലവിൽ ഉൾപ്പെടുത്തിയിരിക്കുന്ന ഫയലുകൾ

- `index.html` — വായനാ ആപ്പ്
- `icon.svg` — PWA ഐക്കൺ
- `manifest.webmanifest` — PWA manifest
- `manifest.json` — അനുബന്ധ manifest പകർപ്പ്
- `sw.js` — Service Worker
- `vercel.json` — Vercel static hosting headers
- `.nojekyll` — GitHub Pages
- `README.md` — നിർദ്ദേശങ്ങൾ

## യഥാർത്ഥത്തിൽ പ്രവർത്തനക്ഷമമാക്കിയ സൗകര്യങ്ങൾ

- 604 പേജുകളുടെ തുടർച്ചയായ സ്ക്രോളിംഗ്.
- പേജ് നമ്പർ നൽകി പോകൽ, മുൻപത്തെ/അടുത്ത പേജ്.
- Quran.com API-യിൽ നിന്നുള്ള QCF V1 വാക്ക് glyphs; ഓരോ പേജിനും അനുയോജ്യമായ font.
- സൂറത്ത് പേരും API metadata-യിൽ `bismillah_pre` ഉള്ളിടത്ത് ബിസ്മില്ലാഹും.
- ഡാർക്ക്/ലൈറ്റ്/സിസ്റ്റം തീം.
- Mushaf Layout തുറന്ന് Quran Text-ന്റെ അറബി ഫോണ്ട് വലുപ്പം കൂട്ടുകയും കുറയ്ക്കുകയും ചെയ്യൽ; വാക്കുകൾ സ്വാഭാവികമായി അടുത്ത വരിയിലേക്ക് മാറും.
- Quran.com API ഉപയോഗിച്ചുള്ള search (നെറ്റ്‌വർക്ക്/API ലഭ്യതയെ ആശ്രയിച്ച്).
- നിലവിലെ പേജ് മനഃപാഠത്തിനായി അടയാളപ്പെടുത്തൽ.
- ഈ ഉപകരണത്തിൽ മാത്രം സൂക്ഷിക്കുന്ന വായനാ പേജ് ചരിത്രവും Dashboard പുരോഗതിയും.
- 604 പേജുകളുടെയും ഡാറ്റയും അനുബന്ധ ഫോണ്ടുകളും IndexedDB-യിൽ ഡൗൺലോഡ് ചെയ്യൽ; തടസ്സപ്പെട്ടാൽ വീണ്ടും ശ്രമിക്കാം.
- PWA ഇൻസ്റ്റാൾ അറിയിപ്പ്; ബ്രൗസർ പിന്തുണയുള്ള Android/desktop-ൽ native prompt, iOS-ൽ Home Screen നിർദ്ദേശം.

## ഈ പതിപ്പിൽ ഉദ്ദേശപൂർവ്വം ഒഴിവാക്കിയവ

- **ഓഡിയോ പ്ലേബാക്ക്:** മുൻ UI-യിലെ audio panel യഥാർത്ഥത്തിൽ സ്ഥിരമായി പ്രവർത്തിക്കുന്നില്ല. Quran Foundation API-യുടെ ഔദ്യോഗിക audio endpoint-ിന് authentication credentials ആവശ്യമാണ്. സുരക്ഷയ്ക്കായി token-ുകൾ പൊതുവായ HTML/JS-ൽ ഇടരുത്. അതിനാൽ പ്ലേ ബട്ടൺ/ഖാരിഅ്/ആവർത്തന demo നീക്കി.
- **വിവർത്തനം:** മുൻ toggle വിവർത്തനം കാണിച്ചിരുന്നില്ല; ഒരു alert മാത്രം ആയിരുന്നു. യഥാർത്ഥ translation data/source ചേർക്കുന്നതുവരെ നീക്കി.
- **ദൈനംദിന reminder/notification:** മുൻ toggle localStorage-ൽ ഒരു മൂല്യം മാത്രം സൂക്ഷിച്ചു; യഥാർത്ഥ scheduled notification അയച്ചില്ല. തെറ്റിദ്ധരിപ്പിക്കാതിരിക്കാൻ നീക്കി.
- **Cloud account, group join/create, cross-device sync:** backend, authentication, database ഇല്ലാതെ പ്രവർത്തിക്കില്ല.
- **Achievement badges, streaks, recitation-time analytics:** കൃത്യമായ event tracking ഇല്ലാതെ യഥാർത്ഥ പുരോഗതി കാണിക്കാനാവില്ല; demo counters ഒഴിവാക്കി.
- **Word-by-word highlighting / tajweed feedback:** audio synchronization, word timing, tajweed rule datasets/engine ഇല്ലാതെ ശരിയായി സാധ്യമല്ല.

## സ്ക്രീൻഷോട്ടിൽ കാണുന്ന അധിക assets

Screenshot-ൽ `DigitalKhattIndoPak.otf`, `indpak-20.csv`, `qpcv1-35.csv`, `word.csv` എന്നീ ഫയലുകളുടെ പേരുകൾ കാണുന്നു. എന്നാൽ screenshot-ൽ പേരുകൾ മാത്രം ആണ്; യഥാർത്ഥ ഫയലുകളുടെ binary/data ഉള്ളടക്കം ഇവിടെ upload ചെയ്തിട്ടില്ല. അതിനാൽ അവയെ package-ൽ കൃത്രിമമായി സൃഷ്ടിച്ചിട്ടില്ല.

- `DigitalKhattIndoPak.otf`: അധിക IndoPak ഫോണ്ട്. QCF V1 page glyph-ുകൾക്ക് പകരം ഇത് സ്വമേധയാ ഉപയോഗിച്ചാൽ അക്ഷര/വാക്ക് glyph mapping തെറ്റാൻ സാധ്യതയുണ്ട്. ഫോണ്ട് ഫയൽ ലഭിച്ചാൽ വേറൊരു font mode ആയി compatibility പരിശോധിക്കാം.
- `indpak-20.csv`: അതിന്റെ column schema/encoding/meaning ലഭിച്ചിട്ടില്ല. upload ചെയ്താൽ പരിശോധിച്ച് mapping ചെയ്യാം.
- `qpcv1-35.csv`: QPC V1 layout/word mapping data ആണോ എന്ന് ഫയൽ പരിശോധിച്ചശേഷം തീരുമാനിക്കണം.
- `word.csv`: വാക്ക്-വാക്കായ ഡാറ്റയാണെങ്കിൽ word selection/highlighting-ന് സഹായിക്കാം; columns, IDs, verse/word key mapping പരിശോധിക്കണം.

ഈ നാലു ഫയലുകളും വേർതിരിച്ച് upload ചെയ്യുക. ലഭിച്ചശേഷം അവയിൽ duplicate/overlap ഉണ്ടോ, ഏത് feature-ന് ഉപയോഗിക്കാം, നിലവിലെ QCF V1 data-യുമായി പൊരുത്തമുണ്ടോ എന്നിവ പരിശോധിച്ച് മാത്രമേ ചേർക്കൂ.

## ഓഡിയോയും മറ്റു ഒഴിവാക്കിയ സൗകര്യങ്ങളും തിരികെ ചേർക്കാൻ വേണ്ടത്

- Audio: ഉപയോഗിക്കാൻ അനുമതിയുള്ള public audio endpoint അല്ലെങ്കിൽ private credentials സൂക്ഷിക്കുന്ന server-side proxy.
- Translation: translation language, provider/API, license/attribution.
- Notifications: PWA push server + subscription storage; അല്ലെങ്കിൽ browser-ൽ പ്രവർത്തിക്കുന്ന local notification schedule-ന്റെ പിന്തുണയും പരിധിയും.
- Cloud sync/groups: backend API, database, user authentication.
- Tajweed/word highlighting: verified word-level timing/alignment data, tajweed annotations, audio synchronization.

## PWA / Offline

HTTPS-ൽ പ്രസിദ്ധീകരിക്കുക. Android/desktop-ൽ install banner/ബ്രൗസർ മെനു ഉപയോഗിക്കുക. iOS Safari-ൽ Share → Add to Home Screen.

ആദ്യമായി ഇന്റർനെറ്റിൽ തുറന്ന് **മുഴുവൻ ഖുർആൻ ഓഫ്‌ലൈനായി സൂക്ഷിക്കുക** അമർത്തുക. 604 പേജുകളുടെ JSON, fonts IndexedDB-യിൽ സൂക്ഷിക്കും. Browser storage മായ്ച്ചാൽ അവ വീണ്ടും download ചെയ്യണം.

## ഉറവിടങ്ങൾ

Quran text/chapter metadata: Quran.com API v4. QCF V1 page fonts: Quran Foundation font CDN. API, font സേവനങ്ങളുടെ ഉപയോഗ നിബന്ധനകൾ ബാധകമാണ്.

വാക്കുകൾക്കിടയിൽ അധിക CSS gap ചേർക്കുന്നില്ല; API glyph-ുകളിൽ ഉള്ള സ്വാഭാവിക സ്പേസ് മാറ്റുന്നില്ല. ഫോണ്ട് വലുപ്പം മാറ്റുമ്പോൾ flex wrapping വഴി വാക്കുകൾ മാത്രം അടുത്ത വരിയിലേക്ക് മാറും. ഒരു വരിയിൽ വാക്കുകളുടെ എണ്ണം സ്ക്രീൻ വീതിയും ഫോണ്ട് വലുപ്പവും അനുസരിച്ച് മാറാം.


## അന്തിമ UI തീരുമാനങ്ങൾ (QCF V1 Modern Islamic)

- Theme: Emerald Islamic, Night Mushaf, System — ഉപയോക്താവിന് തിരഞ്ഞെടുക്കാം.
- ഒരൊറ്റ floating arrow button: അമർത്തുമ്പോൾ Mushaf Layout / Auto Scroll Bottom Sheet തുറക്കും. അത് മുകളിലേക്ക് scroll ചെയ്യുന്ന ബട്ടൺ അല്ല.
- Bottom Sheet-ൽ Quran Text, Arabic Font Size, Auto Scroll Start/Pause/Resume, Speed Control.
- Panel അടച്ചാലും Auto Scroll തുടരുന്നു.
- Auto Scroll നിർത്തിയ സ്ഥാനത്തുനിന്ന് Resume ചെയ്യുന്നു; ഉപയോക്താവ് കൈകൊണ്ട് scroll ചെയ്താൽ സുരക്ഷയ്ക്കായി Auto Scroll pause ചെയ്യും.
- API-യുടെ വാക്കുകളും അവയുടെ spacing-ഉം മാറ്റില്ല; font-size അനുസരിച്ച് വാക്കുകൾ മാത്രം സ്വാഭാവികമായി wrap ചെയ്യും.
