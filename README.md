# Premium Video Popup

A lightweight and responsive JavaScript video popup component designed for promotional videos, announcements, product videos, event promotions, and marketing campaigns.

The popup appears after a configurable delay, slides into view from the bottom-right corner, attempts autoplay, provides a sound fallback when autoplay with audio is blocked, and remembers whether it has already been displayed during the current browser session.

## Demo

**Live Demo:**
https://aminulsarkar.com/video-popup/

**Repository:**
https://github.com/aminulsarkar/premium-video-popup

---

## Features

* Delayed popup appearance
* Smooth slide-in animation
* Smooth slide-out animation
* Responsive design
* Self-hosted MP4 support
* WebM video support
* HTML5 video controls
* Mobile-friendly `playsinline` playback
* Autoplay fallback handling
* Sound/unmute button
* Session-based popup display
* Close button
* Video reset when popup closes
* Video cleanup during navigation
* Video cleanup when the page becomes hidden
* No JavaScript framework required

---

## How It Works

The component follows this sequence:

```text
Page loads
    ↓
Wait for configured delay
    ↓
Display video popup
    ↓
Try autoplay with sound
    ↓
If browser blocks sound
    ↓
Start muted playback
    ↓
Show "Tap for Sound"
    ↓
User can unmute or close
    ↓
Popup remembers display using sessionStorage
```

---

## Technologies

* HTML5
* CSS3
* Vanilla JavaScript
* HTML5 Video API
* Browser Session Storage

No JavaScript framework is required.

---

## Project Structure

```text
premium-video-popup/
│
├── index.html
│
├── css/
│   └── style.css
│
├── js/
│   └── video-popup.js
│
├── assets/
│   ├── favicon.png
│   └── demo.mp4
│
├── README.md
├── PROJECT.txt
├── LICENSE
└── .gitignore
```

---

## Installation

Clone the repository:

```bash
git clone https://github.com/aminulsarkar/premium-video-popup.git
```

Open the project directory and launch `index.html` in your browser.

No build tools or package manager are required.

---

## Adding Your Video

Open `index.html` and replace the video source:

```html
<video
  id="popup-video"
  width="100%"
  controls
  playsinline
>
  <source
    src="assets/demo.mp4"
    type="video/mp4"
  >

  Your browser does not support the video tag.
</video>
```

You can also use a publicly accessible video URL:

```html
<source
  src="https://example.com/video.mp4"
  type="video/mp4"
>
```

---

## Configuration

The main configuration values are located near the top of:

```text
js/video-popup.js
```

### Popup Delay

```javascript
const SHOW_DELAY = 3000;
```

The value is in milliseconds.

For example:

```javascript
const SHOW_DELAY = 5000;
```

displays the popup after 5 seconds.

---

### Animation Duration

```javascript
const ANIMATION_DURATION = 600;
```

This controls how long the popup takes to disappear.

---

## Session-Based Display

The component uses:

```javascript
sessionStorage
```

to remember whether the popup has already appeared during the current browser session.

The storage key is:

```javascript
const STORAGE_KEY = "videoPopupShown";
```

This prevents the video popup from appearing repeatedly while the user navigates through the site during the same session.

To allow the popup to appear again after closing the browser/session, the existing `sessionStorage` behavior can be retained.

---

## Autoplay Handling

Modern browsers may prevent videos with audio from autoplaying.

The component first attempts to play the video with sound.

If the browser blocks autoplay with audio, it falls back to muted playback and displays a:

**🔊 Tap for Sound**

button.

This allows the user to manually enable audio.

---

## Responsive Design

The popup is positioned at the bottom-right of the viewport on desktop devices.

On smaller screens, the popup width is reduced and its spacing is adjusted to keep it within the viewport.

The popup can be further customized through:

```text
css/style.css
```

---

## Navigation Cleanup

The component pauses and resets the video when the user navigates to another page on the same website.

It also resets playback when:

* The page is hidden
* The browser starts unloading the page
* The popup is closed

This helps prevent unwanted video playback from continuing during navigation.

---

## Customization

You can customize:

* Popup width
* Popup position
* Border radius
* Shadow
* Animation duration
* Animation direction
* Mobile dimensions
* Video source
* Popup delay
* Button appearance
* Close button
* Session behavior

The primary styling is located in:

```text
css/style.css
```

The interaction logic is located in:

```text
js/video-popup.js
```

---

## Use Cases

This component can be used for:

* Promotional videos
* Product demonstrations
* Event announcements
* Festival promotions
* Marketing campaigns
* Product launches
* Special offers
* Video advertisements
* Website announcements
* Portfolio demonstrations

---

## Browser Considerations

Autoplay behavior is controlled by individual browsers and may vary depending on whether the video contains audio and whether the user has previously interacted with the website.

The component therefore includes a muted autoplay fallback and a manual sound control.

---

## Author

**Aminul Sarkar**

Website:
https://aminulsarkar.com

GitHub:
https://github.com/aminulsarkar

Senior Full Stack WordPress Developer specializing in WordPress, WooCommerce, PHP, JavaScript, and custom web experiences.

---

## License

This project is released under the MIT License.

See the `LICENSE` file for details.
