# Fridgey

[한국어](README.md) | **English**

A free web app that lists what's in your fridge **by how soon it expires**, with a shopping list in the same place.
No install, no sign-up: just open the link. You can also share **the same fridge** with the people you live with.

### 👉 [Open it now: hong3007.github.io/Fridgey](https://hong3007.github.io/Fridgey/)

<!-- Screenshot slot: add phone screenshots below, e.g. ![Fridge screen](docs/screen-fridge.png) -->

## Highlights

- **Fast entry.** Type a food name and a date (`261020` = YYMMDD), then press Enter. Names you use often show up as suggestions while you type; tap one to add it.
- **Most urgent first.** Items are sorted by expiry date, and the days left are color-coded.
- **Shopping list.** Set a quantity, check off what you bought, and move it all into the fridge at once.
- **Share it.** Everyone holding the key file sees the same fridge. Changes usually show up on the other phone within 30 seconds.
- **Make it yours.** Rename sections (Shelf 1, Shelf 2, …) and the app, tab, field and button names, pick one of 5 themes, and switch between **English and Korean** in Settings.
- **Mistakes are fine.** Tap "Done" on an item you finished; it goes to the Bin, where you can restore it.

## Getting started

1. Open the link above.
2. On the **key file screen** that appears first, save your key file (sending it to yourself in a messenger works well).
3. Type a food name and a date, then tap **Add**.

To share, send your saved key file to the other person. They open the link and tap **"I already have a key file (join)"** to open the same fridge.

### Add to home screen

- **iPhone**: open it in Edge and choose **Add to Home Screen** from the menu (Share), or open the link straight from a KakaoTalk chat.
- **Android**: in Chrome, use **Add to Home screen** (or **Install app**) from the menu.

> Each browser keeps its own storage, so opening the app in a different browser for the first time starts a new, separate fridge. To keep using the same one, join with your key file.

## How is my data stored?

- What you enter is **encrypted on your phone** and then backed up to a server (the free storage service [Supabase](https://supabase.com)).
- The server only holds **unreadable ciphertext**. The **key file never goes to the server**, so even the server owner can't see your items.
- **Anyone with the key file** (including anyone who can access the messenger or cloud account where you keep it) can read and edit the fridge, so check who you send it to.
- Every fridge has its own key, so other people using the same app link never see each other's fridges.
- This repository (GitHub) contains **only the app code**, no user data.

## Good to know

- **If you lose both the key file and the key stored on your devices, the fridge can't be recovered.** Not even its creator can open it.
- Clearing your browser's cookies/site data also removes the key from your phone. Join again with your saved key file to bring everything back.
- Up to 300 fridge items and 300 shopping items; the Bin keeps the latest 100.
- It runs on a free service, so if the server is paused, syncing stops until it's back; each phone keeps working on its own. You can also back up your data to a file with **Export data** in Settings (the exported file is not encrypted, so keep it somewhere safe).

## Tech notes (for the curious)

- Runs from **a single `index.html` file** with no build step. No external libraries; only the font (Gowun Dodum) is loaded from Google Fonts.
- Hosted on GitHub Pages.
- Encryption uses the browser's built-in WebCrypto (AES-GCM). From the key file, the app derives two separate values: a room ID and an encryption key. The server stores only the room ID and the ciphertext; its table can't be read or written directly, and only two read/write functions are exposed.
- The server-side setup is managed separately by the app's maker, not in this repository.

## License

[MIT License](LICENSE)
