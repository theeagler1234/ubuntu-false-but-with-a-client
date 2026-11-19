# ubuntu-false-but-with-a-client

A standalone browser-based launcher for the [ubuntu-false](https://github.com/theeagler1234/ubuntu-false) webtop project.

## `client.html`

`client.html` is a self-contained local web client that opens a deployed ubuntu-false instance from a desktop browser. It is not the Ubuntu webtop server itself; it provides a control page for connecting to one.

### Getting started

1. Download or clone this repository.
2. Start an ubuntu-false/webtop instance and note its address and port.
3. Open `client.html` directly in a browser.

No build step or separate web server is required. The page is designed to run from a `file://` URL and uses browser-based local storage for its settings.

### Connecting

Enter an IP address, hostname, or full reverse-proxy URL, along with the `http://` or `https://` protocol. The page also includes quick presets for ports commonly used by webtop deployments:

- `3000` — HTTP
- `3001` — HTTPS
- `6901` — HTTPS/Kasm

The **Test** button performs a best-effort reachability check. **Launch Pop-up Webtop** opens the target in a separate application-like browser window, while **Embed View** displays it inside an iframe on the page.

### Features

- Configurable window size for pop-up sessions
- Optional HTTP basic-auth user and password fields
- Saved server/bookmark management using `localStorage`
- Remembers the most recently used address and protocol
- Embedded viewport with reload, fullscreen, and close controls
- Clipboard-synchronization helper for an active pop-up window
- Browser and GPU capability detection
- WebGL/WebGPU/WebCodecs status diagnostics
- Toast notifications for connection and browser events

### Browser permissions

Opening the page as a local file can limit clipboard, WebGPU, and other browser features. When prompted, allow pop-ups and the requested permissions for the page. Some browsers also restrict or block cross-origin iframe content, clipboard access, and embedded authentication.

### Important graphics note

The client detects WebGL, WebGPU, and WebCodecs support in the local browser. These capabilities describe the browser and device; they do not automatically transfer GPU or OpenGL rendering into the remote ubuntu-false server. The actual rendering model depends on how the webtop deployment is configured and the streaming technology it uses.

## Project link

- Ubuntu-false: https://github.com/theeagler1234/ubuntu-false
