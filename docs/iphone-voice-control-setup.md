# iPhone XR Voice Control Setup for Hospital Audio

This document captures the practical setup for turning an old iPhone XR into a simple bedside audio/video device for an elderly, legally blind Korean speaker.

The goal is **not** to make the whole iPhone independently navigable. The goal is to make a few reliable Korean voice commands work:

- `시리야, 뉴스 틀어줘.`
- `시리야, 가족 영상 틀어줘.`
- `시리야, 클래식 틀어줘.`
- `시리야, 도움말 틀어줘.`

The iPhone should behave like a small audio appliance. Complexity belongs on the family/Mac side, not on the patient side.

---

## 1. Intended architecture

### Patient-facing layer

Use only a few simple surfaces:

- **Apple Music** for local classical music and instruction recordings.
- **YouTube** for family-added videos and some Korean news/current-affairs content.
- **Podcasts** optionally for Korean news/economy/culture shows.
- **Siri** for launching major categories.
- **Voice Control** for fallback actions such as `탭 재생`, `숫자 표시`, and `홈으로 가`.
- **VoiceOver** only as an emergency/navigation tool, not necessarily always on.

### Family/media-management layer

Family members can add videos to a shared/collaborative YouTube playlist such as:

- `아버지께 드릴 영상`
- `가족 추천 영상`

If family conflict becomes a problem, split into two playlists later. Start with one playlist first.

---

## 2. Prepare the iPhone basics

On the iPhone XR:

1. Connect to reliable Wi‑Fi.
2. Sign into YouTube if family playlists will be used.
3. Confirm that the shared YouTube playlist opens correctly.
4. Open Apple Music and confirm the local classical playlists work.
5. Confirm the charging cable and headphone/DAC setup works.
6. In **Settings → Siri**, enable:
   - Listen for “Siri” / “Hey Siri”
   - Allow Siri When Locked
7. Set Siri language to Korean if he will use Korean commands.

Recommended physical setup:

- iPhone plugged in continuously.
- Headphones or speaker connected.
- Screen brightness low if not visually needed.
- Notifications minimized.
- Unneeded apps moved away or deleted.

---

## 3. Create the core Shortcuts

Open **Shortcuts** on the XR and create these shortcuts.

### Shortcut: `뉴스 틀어줘`

Use this for a YouTube news playlist, podcast, or other news source.

Actions:

1. **URL** — paste the chosen YouTube playlist/video-in-playlist URL or podcast/news URL.
2. **Open URLs**

Name the Shortcut exactly:

```text
뉴스 틀어줘
```

Test:

```text
시리야, 뉴스 틀어줘.
```

---

### Shortcut: `가족 영상 틀어줘`

Use this for the shared family YouTube playlist.

Actions:

1. **URL** — paste the shared family YouTube playlist URL. A video URL with playlist context is often better than a bare playlist URL:

```text
https://www.youtube.com/watch?v=VIDEO_ID&list=PLAYLIST_ID
```

2. **Open URLs**

Name:

```text
가족 영상 틀어줘
```

Test:

```text
시리야, 가족 영상 틀어줘.
```

---

### Shortcut: `클래식 틀어줘`

Best target: a local Apple Music playlist of preloaded classical music.

Possible actions:

1. **Play Music**
2. Choose the classical playlist.

Name:

```text
클래식 틀어줘
```

Test:

```text
시리야, 클래식 틀어줘.
```

---

### Shortcut: `도움말 틀어줘`

Best target: a local Apple Music playlist containing instruction recordings.

Recommended playlist name:

```text
도움말
```

Recommended first track name:

```text
도움말 — 먼저 들으세요
```

Shortcut action:

1. **Play Music**
2. Choose the `도움말` playlist or instruction track.

Name:

```text
도움말 틀어줘
```

Test:

```text
시리야, 도움말 틀어줘.
```

---

## 4. Turn on Voice Control

Voice Control is different from VoiceOver.

- **VoiceOver** changes touch gestures and reads the screen.
- **Voice Control** lets the user operate the phone by speaking commands.

On the XR:

1. Open **Settings**.
2. Go to **Accessibility**.
3. Tap **Voice Control**.
4. Tap **Set Up Voice Control** if shown.
5. Turn **Voice Control** on.
6. Download any required language files.
7. Set language to Korean if available and appropriate.

Once enabled, test commands such as:

```text
탭 재생
탭 일시 정지
홈으로 가
숫자 표시
격자 표시
아래로 스크롤
```

Exact Korean command recognition may vary depending on iOS language and Siri/Voice Control settings. Test the actual phrases on the phone and adjust the instruction recording to match what works.

---

## 5. Create custom Voice Control commands

Go to:

**Settings → Accessibility → Voice Control → Customize Commands → Create New Command**

Create short commands that run the Shortcuts.

### Command: `뉴스`

- **Phrase:** `뉴스` or `뉴스 틀어줘`
- **Action:** Run Shortcut
- **Shortcut:** `뉴스 틀어줘`

### Command: `가족 영상`

- **Phrase:** `가족 영상`
- **Action:** Run Shortcut
- **Shortcut:** `가족 영상 틀어줘`

### Command: `클래식`

- **Phrase:** `클래식`
- **Action:** Run Shortcut
- **Shortcut:** `클래식 틀어줘`

### Command: `도움말`

- **Phrase:** `도움말`
- **Action:** Run Shortcut
- **Shortcut:** `도움말 틀어줘`

Use short phrases. They may be easier for an elderly user to remember and pronounce than full polite sentences.

---

## 6. Fallback voice commands

Teach only a small fallback vocabulary.

Important commands:

```text
탭 재생
탭 일시 정지
다음
멈춰
계속 재생
소리 키워
소리 줄여
홈으로 가
숫자 표시
격자 표시
```

Most important fallback:

```text
숫자 표시
```

This overlays numbers on tappable controls. Then the user can say the desired number.

Second fallback:

```text
격자 표시
```

This overlays a grid for more precise screen control.

For YouTube specifically:

- `가족 영상 틀어줘` should open the playlist.
- If YouTube does not autoplay, say `탭 재생`.
- If the screen is confusing, say `숫자 표시` and select the visible play button by number.

---

## 7. VoiceOver setup

VoiceOver is useful but disruptive for sighted helpers because it changes normal gestures.

Recommended approach:

- Keep VoiceOver **off by default**.
- Make it easy to toggle when needed.

Go to:

**Settings → Accessibility → Accessibility Shortcut**

Select only:

```text
VoiceOver
```

Then triple-click the side button to toggle VoiceOver.

Also test:

```text
시리야, VoiceOver 켜 줘.
시리야, VoiceOver 꺼 줘.
```

---

## 8. Shared YouTube playlist setup

Start with one collaborative playlist.

Suggested name:

```text
아버지께 드릴 영상
```

or:

```text
가족 추천 영상
```

Recommended visibility:

```text
Unlisted
```

Setup:

1. Create the playlist from the admin/librarian YouTube account.
2. Set it to Unlisted.
3. Enable collaboration/invite collaborators.
4. Send invite link to family members.
5. Family members accept once.
6. After that, when they find a video in their own YouTube account, they can use **Save → 아버지께 드릴 영상**.

Family rule:

```text
아버지께서 좋아하실 만한 영상만 넣어 주세요. 목록은 너무 길어지지 않게 가끔 정리하겠습니다.
```

If family conflict appears, later split into two playlists and two commands.

---

## 9. Instruction recording

Make a Korean audio file and import it into Apple Music.

Recommended track name:

```text
도움말 — 먼저 들으세요
```

Recommended playlist name:

```text
도움말
```

Then the user can say:

```text
시리야, 도움말 틀어줘.
```

### Korean instruction script

Record this slowly, with pauses after each command.

```text
이 아이폰은 음악, 뉴스, 가족 영상을 듣고 보는 기계입니다.

뉴스를 들으시려면 이렇게 말씀하세요.

“시리야, 뉴스 틀어줘.”

클래식 음악을 들으시려면 이렇게 말씀하세요.

“시리야, 클래식 틀어줘.”

가족이 보내 준 영상을 보시려면 이렇게 말씀하세요.

“시리야, 가족 영상 틀어줘.”

사용 방법을 다시 듣고 싶으시면 이렇게 말씀하세요.

“시리야, 도움말 틀어줘.”

유튜브가 열렸는데 재생이 안 되면 이렇게 말씀하세요.

“탭 재생.”

멈추고 싶으시면 이렇게 말씀하세요.

“멈춰.”

다시 들으시려면 이렇게 말씀하세요.

“계속 재생.”

다음 곡이나 다음 영상을 들으시려면 이렇게 말씀하세요.

“다음.”

소리를 키우고 싶으시면 이렇게 말씀하세요.

“소리 키워.”

소리를 줄이고 싶으시면 이렇게 말씀하세요.

“소리 줄여.”

화면이 이상하거나 길을 잃은 것 같으면 이렇게 말씀하세요.

“홈으로 가.”

버튼을 고르기 어려우면 이렇게 말씀하세요.

“숫자 표시.”

그러면 화면의 버튼들에 번호가 보입니다. 그 다음 원하는 번호를 말하면 됩니다.

전화기는 계속 충전기에 꽂아 두셔도 됩니다.

잘 안 되면 가족이나 간호사님께 도움을 요청하세요.
```

Important: when recording, say command examples clearly but not too quickly. If the recording itself accidentally triggers Siri, re-record with phrasing like:

```text
다음 문장을 말씀하세요: “시리야, 뉴스 틀어줘.”
```

---

## 10. Printed bedside card

Even if he cannot read it, a nurse or family member can.

Suggested card:

```text
아이폰 사용 방법

시리야, 뉴스 틀어줘
시리야, 가족 영상 틀어줘
시리야, 클래식 틀어줘
시리야, 도움말 틀어줘

안 되면:
탭 재생
숫자 표시
홈으로 가

전화기는 충전기에 계속 꽂아 두세요.
```

---

## 11. Testing checklist

Test each item on the actual XR, in Korean, before leaving the phone with him.

### Siri / Shortcuts

- [ ] `시리야, 뉴스 틀어줘` opens the intended news source.
- [ ] `시리야, 가족 영상 틀어줘` opens the shared YouTube playlist.
- [ ] `시리야, 클래식 틀어줘` starts local classical music.
- [ ] `시리야, 도움말 틀어줘` plays the instruction recording.

### Voice Control fallback

- [ ] `탭 재생` works when YouTube is open.
- [ ] `홈으로 가` works.
- [ ] `숫자 표시` works.
- [ ] `격자 표시` works.

### Audio / power

- [ ] Phone charges while in use.
- [ ] Headphones/speaker work.
- [ ] Volume is safe and audible.
- [ ] Phone stays connected to Wi‑Fi.

### Family playlist

- [ ] Shared playlist exists.
- [ ] At least one family member can add a video from their own account.
- [ ] XR shortcut opens the playlist.
- [ ] Playlist is not empty.

---

## 12. Design principle

Keep the patient interface tiny.

Do not expose a full media library, app interface, or family control panel to the patient.

The stable command set should remain:

```text
시리야, 뉴스 틀어줘.
시리야, 가족 영상 틀어줘.
시리야, 클래식 틀어줘.
시리야, 도움말 틀어줘.
```

All complexity should live elsewhere:

- family YouTube playlist,
- Mac-side music/news preparation,
- optional future Samhan control-center app,
- admin/librarian workflow.
