# کورد ئیمەیج کویز — Kurd Image Quiz

وێبسایتێکی سادەیە کە وێنەیەک وەردەگرێت و بە یارمەتی Gemini AI کویزێکی تایبەت لێی دروست دەکات.

## خاڵی سەرەکی ئەم وەشانە
- **زمانی ڕووکار (UI)** و **زمانی پرسیارەکان (Quiz language)** بە تەواوی جیاواز و سەربەخۆن:
  - دوگمەکانی سەرووی لاپەڕە (EN / عربي / Türkçe / کوردی) تەنیا **دیزاینی ماڵپەڕەکە** دەگۆڕن (ناونیشان، دوگمەکان، ڕێنماییەکان...).
  - چیپەکانی "هەڵبژاردنی زمان" لەناو ڕێکخستنەکاندا تەنیا **زمانی پرسیارە دروستکراوەکان** دیاری دەکەن، کاریگەری لەسەر ڕووکاری ماڵپەڕەکە نییە.
- ئایکۆنی وێنەی مێشک (ئەوەی نێردرا) وەک ئایکۆنی PWA بەکارهاتووە، بۆیە کاتێک بەکارهێنەر "Add to Home Screen" دەکات، هەر ئەم ئایکۆنە دەردەکەوێت.

## چۆنیەتی بەڕێوەبردن لەسەر GitHub Pages
1. ڕیپۆیەکی نوێ لە GitHub دروست بکە (بۆ نموونە `kurd-image-quiz`).
2. هەموو فایلەکانی ئەم فۆڵدەرە (`index.html`, `manifest.json`, `sw.js`, `icons/`) بار بکە (upload) بۆ ڕیشەی ڕیپۆکە.
3. بچۆ سەر **Settings → Pages**، لە بەشی *Branch* گۆڕانکاری `main` و فۆڵدەری `/ (root)` هەڵبژێرە، پاشان **Save** بکە.
4. دوای چەند خولەک لینکەکەت لەسەر شێوەی
   `https://USERNAME.github.io/kurd-image-quiz/` چالاک دەبێت.

## کلیلی Gemini API — تەنیا یەک جار دایبنێ
ئێستا پێویست ناکات هەر بەکارهێنەرێک کلیلی خۆی دابنێت. تۆ وەک خاوەنی ماڵپەڕەکە تەنیا **یەک جار** لەناو کۆدەکەدا کلیلەکە دادەنێیت و هەموو سەردانکەرەکان بەخۆکار بەکاری دەهێنن:

1. لە [aistudio.google.com/app/apikey](https://aistudio.google.com/app/apikey) کلیلێکی بێبەرامبەر وەربگرە.
2. فایلی `index.html` بکەرەوە، لە سەرەتای بەشی `<script>` ئەم دێڕە بدۆزەرەوە:
   ```js
   const BUILT_IN_API_KEY = "PASTE_YOUR_GEMINI_API_KEY_HERE";
   ```
   و لەنێوان کاوانەکاندا کلیلەکەی خۆت دابنێ، بۆ نموونە:
   ```js
   const BUILT_IN_API_KEY = "AIzaSyXXXXXXXXXXXXXXXXXXXXXXXXXXXXX";
   ```
3. فایلەکە پاشەکەوت بکە و بیخەرە سەر GitHub. تەواو — ئیتر هیچ ئایکۆنی ڕێکخستن یان داواکاری کلیل بۆ سەردانکەرەکان نیشان نادرێت.

⚠️ **تێبینی گرنگ**: ئەمە ماڵپەڕێکی static و گشتییە (GitHub Pages)، واتا هەر کەسێک سەیری سەرچاوەی لاپەڕەکە (view-source) بکات دەتوانێت کلیلەکەت ببینێت و بەکاریبهێنێت. تەنیا بۆ پڕۆژەی کەسی یان بچووک باشە. ئەگەر دەتترسی لە خەرجی زیادە، لە Google AI Studio سنووری بەکارهێنان (usage limit) بۆ کلیلەکە دابنێ.

## گۆڕینی ئایکۆن
ئایکۆنەکان لە فۆڵدەری `icons/` هەن (`icon-192.png`, `icon-512.png`, `apple-touch-icon.png`, `favicon-32.png`). ئەگەر ویستت ئایکۆنێکی تر بەکاربهێنیت، هەمان ناوی فایلەکان بەکاربهێنە یان `manifest.json` و `index.html` نوێ بکەرەوە.

---

### Quick summary (EN)
Static, single-page quiz generator: upload an image → Google Gemini Vision (called client-side with your own free API key) reads it and writes a quiz in the language you pick. The top-bar language switcher changes **only the interface text**; the "Question language" chips inside the settings card change **only the language of the generated quiz** — the two are fully independent, which was the bug in the previous version. The uploaded brain-icon PNG is baked in as the PWA icon (manifest + apple-touch-icon), so "Add to Home Screen" shows that icon. Just push these files to a GitHub repo and enable GitHub Pages (Settings → Pages → deploy from `main` / root).
