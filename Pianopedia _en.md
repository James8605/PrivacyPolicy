# Privacy Policy

**App:** Pianopedia 
**Effective date:** 2026-05-09
**Last updated:** 2026-05-09

This policy describes how Pianopedia (the "app") handles your data. Pianopedia is designed to work without an account and to keep your data on your device by default. This policy applies to the iOS app distributed through the App Store.

---

## Summary

- Pianopedia does not require sign-up or an account.
- The app does not collect analytics, advertising identifiers, location, or contacts.
- The microphone is used only to detect the pitch you play. Audio is processed on the device in real time and is not recorded, saved, or uploaded.
- The camera and photo library are used only to import sheet music you choose to scan.
- Cloud sheet recognition is opt-in. When enabled, the photo of the sheet you choose to scan is sent to the LLM Provider API using an API key that you provide. Pianopedia does not relay this data through any server we operate.
- Your library, practice history, and settings are stored locally on your device.

---

## What data the app handles

### 1. Microphone audio (real-time, not retained)

When you start a practice session, the app uses the microphone to detect the pitch and timing of what you play. Audio samples are processed on the device using a standard pitch-detection algorithm and are discarded immediately. Pianopedia does not record audio to disk and does not transmit audio off the device.

### 2. Photos and camera input

You can import sheet music from the camera, the photo library, or the iOS document scanner. The app reads only the images you explicitly choose during an import action. Imported images are kept on the device only as long as needed to extract a playable score, and the resulting score is then stored in your local library.

### 3. Cloud sheet recognition (optional, opt-in)

The on-device recognizer can read numbered notation (jianpu) without a network connection. For best results on staff notation and complex layouts, the app offers an optional cloud recognition path that uses LLM Provider's Claude API.

To use cloud recognition, you must:

1. Obtain your own API key from LLM Provider.
2. Enter the key in **Settings -> Cloud Recognition**.

When cloud recognition is enabled and you trigger a scan:

- The chosen sheet image is downscaled to roughly 1024 pixels and JPEG-compressed locally.
- The image and a recognition prompt are sent directly from your device to the LLM Provider API endpoint, authenticated with your API key.
- The structured score returned by the API is parsed locally and saved to your library.

Pianopedia does not operate any intermediate server. LLM Provider's processing of the request is governed by their own terms and privacy policy. Pianopedia does not control how LLM Provider handles the request data; please review LLM Provider's documentation for details.

If you do not enable cloud recognition (no API key stored), no images leave your device.

### 4. API key storage

If you choose to enable cloud recognition, your LLM Provider API key is stored in the iOS Keychain on your device (`kSecClassGenericPassword`, accessibility `kSecAttrAccessibleAfterFirstUnlock`, not marked synchronizable). The key is not included in iCloud Keychain sync, is not transmitted to any Pianopedia server (we do not operate one), and is sent only to the LLM API endpoint when you trigger a scan. You can remove the key at any time from **Settings -> Cloud Recognition -> Remove key**.

### 5. Library and practice history

Sheets you import or edit, your practice history (per-session score, timing accuracy, completion rate, per-note results, duration, date), preferences (theme, language, notation style), and onboarding state are stored locally in the app's sandbox. These data are not uploaded to Pianopedia or to any third party.

If you have iCloud Backup enabled for the device, the operating system may include the app's container in encrypted device backups managed by Apple. Pianopedia does not control or read these backups.

### 6. Network requests

Pianopedia makes outbound network requests only when you take an action that requires them:

- **Discover / Search:** searching the in-app catalog issues HTTP requests to public score libraries (for example, Mutopia Project and piano-midi.de) and to any custom catalog URL you paste in Settings. Requests contain only your search query and standard HTTP headers.
- **Cloud sheet recognition:** described above. Requires your API key and only fires when you scan a sheet with the cloud path enabled.
- **Score downloads:** when you import a piece from a search result, the corresponding MIDI / MusicXML / JSON file is fetched from the public URL listed in the result.

The app does not contact any analytics, advertising, or telemetry endpoint.

---

## Permissions

| Permission     | Purpose                                                                  |
|----------------|--------------------------------------------------------------------------|
| Microphone     | Listen to your playing for real-time pitch detection during practice.    |
| Camera         | Capture photos of sheet music to import.                                 |
| Photo Library  | Read photos you select when importing existing sheet music.              |

You can revoke any of these permissions at any time in **iOS Settings -> Pianopedia**. The app will continue to function in modes that do not require the revoked permission.

---

## Data we do not collect

- We do not collect or store user accounts, names, email addresses, or phone numbers.
- We do not collect device identifiers for advertising (IDFA), location data, contacts, calendars, or health data.
- We do not include third-party analytics, crash reporting, or advertising SDKs.
- We do not track you across apps or websites.

---

## Children

Pianopedia is suitable for general audiences, including children, and does not collect personal information from anyone, including children under 13. The microphone is used only for on-device pitch detection during practice sessions, and audio is never recorded or transmitted.

If you (or your child) choose to enable cloud sheet recognition, please note that requests to the LLM Provider API are governed by LLM Provider's terms; we recommend a parent or guardian configures and manages the API key.

---

## Data retention and deletion

All data managed by the app lives in the app's local container on your device. To remove all app data, uninstall Pianopedia from your device. Removing the API key from **Settings -> Cloud Recognition** deletes it from the Keychain.

---

## Security

- The LLM Provider API key, when stored, is held in the iOS Keychain.
- Network requests to score libraries and to the LLM Provider API use HTTPS.
- Audio processing and scoring run entirely on the device.

No system can be guaranteed fully secure, but we follow standard iOS practices for credential storage and network transport.

---

## Changes to this policy

If we change how the app handles data, we will update this policy and revise the "Last updated" date above. Material changes will also be reflected in the App Store release notes.

---

## Contact

If you have questions about this policy or the app's privacy practices, please contact:

**Email:** zhangyang8605@gmail.com
