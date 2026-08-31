# Privacy Policy — Air 2 3D Lab

**Last updated:** 31 August 2026

**App:** Air 2 3D Lab (`com.xreal.handshapes`)  
**Developer:** ToolsForTheMasses  
**Contact:** cezar.lucan@gmail.com

This privacy policy describes how Air 2 3D Lab (“the App”) handles information when you use it on an Android phone with XREAL glasses.

---

## Summary

- The App does **not** require an account.
- The App does **not** sell your data.
- The App does **not** use advertising or analytics SDKs to profile you.
- Almost all content you create or import stays **on your device** (or on files you choose to share yourself).
- **Voice is optional.** If you enable it, enter your own LLM API key, and tap **Send**, the prompt (and sometimes a downscaled JPEG) goes to the **provider you chose** — not to us. Core 3D editing works with Voice off.

---

## Information the App uses

### On-device files you provide

You may choose to:

- Pick a **Home folder** (via Android’s Storage Access Framework) to browse and load **STL** / glTF models, **image textures** (on meshes), and **Image** photo plates. If you ask the Voice assistant to **save an image**, the App may **write a PNG** into that same Home folder.
- **Share** local **video** files into the App for the Video screen. Share opens a lightweight on-device list (not the glasses session) and copies the file into app storage. You can delete those copies from that list.
- **Save / load** named environments and export / import `.hse` packages.
- Capture **screenshots** (and optional recordings) saved to app storage / Pictures.

These files are processed **locally**. The App does not upload them to our servers. We do not operate a cloud backend for this App.

### Camera (optional)

If you enable the **camera background** feature, the App may access the phone camera or glasses RGB camera to show a live background in mixed reality. Camera frames are used **only for display on your device** while the feature is on. They are not recorded by that feature for upload, and they are not sent to us.

### Network

The App may use network permission for:

- An **optional local Wi‑Fi stream** of your view (MJPEG) that you start yourself, typically so another device on the **same local network** (for example VLC) can preview the view. This stream stays on your LAN unless you expose it yourself.
- Normal Android / Play Store connectivity.
- An **optional Voice assistant**: only after you enable it, enter your own cloud LLM API key, and tap **Send** on the editable prompt. The App then sends the prompt text (and tool results) over **HTTPS** to the **provider you chose** (Gemini, Claude, OpenAI, Kimi, or xAI). If the assistant calls **look_at_image** or **draw_on_image** with a preview, a **downscaled JPEG** of that photo/canvas is included so a vision model can see or check the drawing. If you tap **Attach view** on Send, or the assistant calls **capture_view**, **look_at_view**, or **click_ui** with preview, a **downscaled JPEG of the current mixed-reality view** is included. We do not operate that cloud and do not receive a copy. Speech-to-text runs **on-device** and is **not** uploaded until you explicitly send the edited text. Raw microphone audio is never uploaded.

The App does not require internet access for core 3D editing, mates, sketch tools, or local STL / image loading.

### Microphone (optional)

If you use the Voice assistant **Mic** control, the App requests **RECORD_AUDIO** so Android’s on-device speech recognizer can turn speech into text. Audio is processed on the device for recognition; the App does not upload raw audio to the developer. The resulting text stays in the editable prompt until you tap **Send**.

### Device / media controls

The Music player shape can send **media key** and **volume** commands to the active music app on your phone. That stays on-device between Android components; we do not receive your playlists or listening history.

### Preferences

The App may store simple preferences on the device (for example Home folder display path, select-hold time, axes offsets, capture resolution, Voice enable flag, chosen LLM provider, and the API key you entered) using Android / Unity local storage (such as SharedPreferences / PlayerPrefs). The API key is stored only on your device and is sent only to the LLM provider you selected when you submit a prompt. You can export a password-protected `.hsb` backup (Menu → Environment → **Backup**) that includes those keys, triad/handle offsets, and Home metadata — not saved environments; **Restore** decrypts it only with the password you chose.

---

## Information we do not collect

We do not intentionally collect:

- Name, email, or account credentials (no login)
- Precise location for our own use
- Contacts, SMS, or call logs
- Advertising IDs for ads (the App has no ads)
- Analytics event streams to third-party analytics vendors for profiling

Google Play may collect standard install / crash / distribution data under Google’s own policies when you download the App from Play. That is controlled by Google, not by a separate analytics SDK we ship for marketing.

---

## Children

The App is not directed at children under 13. Do not use the App if you are under the age required by local law for consent without a parent/guardian.

---

## Data sharing

We do not sell personal information.  
We do not share your STLs, videos, environments, or camera feed with third parties through the App.

If you enable the Voice assistant and tap **Send**, that is a **user-initiated** request: the prompt text (and tool results needed for that request) are sent to the **cloud LLM provider you configured** under that provider’s terms. We do not operate that backend. That payload can include a JPEG when you ask the assistant to look at or draw on a photo, or to look at the live view (`capture_view` / `look_at_view`, or **Attach view** on Send).

You may choose to share files yourself (for example exporting a `.hse` layout package, a password-protected `.hsb` settings backup, or using the Android share sheet).

---

## Google Play Data safety

On Google Play we declare **optional collection** of:

- **Other user-generated content** — Voice prompt text (and related tool text) when you tap Send.
- **Photos** — a downscaled JPEG only when a vision tool or **Attach view** includes one.

Both are for **app functionality**, processed **ephemerally** by the App (we do not keep a server copy), and **not required** to use the App. We do not declare sharing with third parties because Send is a specific action you start, to a provider you configured. Camera frames, microphone audio, videos, and Home files stay on the device unless you send a Voice prompt that includes a JPEG as described above.

---

## Data retention

Content stays on your device until you delete it, clear app data, or uninstall the App. Uninstalling removes app-private storage (including a stored API key); files you saved to shared folders (for example Pictures or a Home folder you manage) remain until you delete them.

We do not operate a cloud store of your prompts or photos, so there is nothing on our servers to delete. The LLM provider you chose may retain request data under **their** terms — revoke the key and use that provider’s account/deletion tools if you need that copy removed.

---

## Your choices

- Deny camera permission — core App use continues without the camera background.
- Deny microphone permission — Voice Mic stays unavailable; you can still type in the prompt if Voice is enabled.
- Leave Voice off / do not enter an API key — no prompts are sent to cloud LLM providers.
- Do not pick a Home folder or share videos — those features simply stay unused.
- Revoke permissions in Android Settings at any time.
- Clear app storage or uninstall to remove app-private data (including a stored API key).

---

## Security

We rely on on-device processing and Android platform protections. Voice Send uses **HTTPS** to the provider you selected. API keys you enter for the Voice assistant are stored on-device; treat them like passwords and revoke them at the provider if the device is lost. A **Backup** `.hsb` is encrypted with a password you type at export; anyone with the file still needs that password to **Restore** (and thus to read the keys). No method of electronic storage is 100% secure; keep your device locked, choose a strong backup password, and only share packages with people you trust.

---

## Changes

We may update this policy when the App’s behavior changes. The “Last updated” date at the top will change. Continued use after an update means you accept the revised policy.

---

## Contact

Questions about this policy: **cezar.lucan@gmail.com**

---

*This policy is provided for the Google Play listing of Air 2 3D Lab. It is not legal advice. Keep the public HTTPS URL in Play Console pointed at this current text.*
