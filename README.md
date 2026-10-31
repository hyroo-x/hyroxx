<h1 align="center">
  <img alt="Hyrox logo" src="https://raw.githubusercontent.com/Hyro03/logo-ai/main/baileys.jpg" height="250" />
</h1>

<h1 align="center">Hyrox</h1>

<p align="center"><strong>A Custom Baileys Fork with Button & Native Flow Support</strong></p>
<p align="center">Built for developers. Designed for flexibility.</p>

Hyrox is a custom Baileys fork built for WhatsApp bot development, based on WhiskeySockets Baileys "7.0.0-rc14", with additional development focused on interactive messaging and Native Flow support.

Hyrox hadir untuk developer yang membutuhkan fleksibilitas lebih dalam membangun WhatsApp bot, terutama dalam pengembangan message handling, interactive messages, dan integrasi fitur bot.

<p align="center"><em>«One package. More flexibility. Built for your bot.»</em></p>

---

## About Hyrox

Hyrox is an independent project created to extend and customize the Baileys experience for WhatsApp bot developers.

Using WhiskeySockets as its foundation and Itsliaaa's implementation as a reference for interactive messaging, Hyrox aims to provide a practical development experience for projects that need flexible message handling.

Bukan sekadar package biasa — Hyrox dikembangkan dengan fokus pada customization, compatibility, dan developer experience.

### Key Highlights

- **Baileys-Based Architecture** — Built on WhiskeySockets Baileys "7.0.0-rc14".
- **Interactive Messaging** — Development support for interactive message formats.
- **Native Flow** — Additional work focused on Native Flow payloads.
- **Developer Friendly** — Designed for Node.js projects using JavaScript ESM.
- **Flexible Integration** — Can be installed under the package alias "baileys".
- **Open Development** — Built with references to existing open-source implementations.

## ✨ Feature List

### 🔌 Connection & Authentication

- 📡 WhatsApp Web Connection
- 📱 Multi-Device Support
- 📷 QR Code Authentication
- 🔢 Pairing Code Authentication
- 🔐 Authentication State Management
- 💾 Session Reuse
- 🔄 Reconnection Handling
- 📶 Connection Update Events
- 🚪 Logout Support

### 💬 Messaging System

- 📝 Text Messages
- 💭 Quoted Messages
- ↩️ Reply Messages
- 🖼️ Image Messages
- 🎬 Video Messages
- 🎵 Audio Messages
- 🎙️ Voice Notes
- 📄 Document Messages
- 🎨 Sticker Messages
- 👤 Contact Cards
- 📍 Location Messages
- 🗺️ Live Location Messages
- ❤️ Reaction Messages
- 📊 Poll Messages
- ↪️ Forwarded Messages
- 🧩 Message Context & Metadata
- 🆔 Message ID & Key Utilities

### 🔘 Buttons & Interactive Messaging

- 🔘 Button Message Formats
- ⚡ Interactive Message Support
- 🌊 Native Flow Support
- 🧷 Template Button Formats
- 💬 Quick Reply Buttons
- 🔗 CTA URL Buttons
- 📋 CTA Copy Code Buttons
- 🛠️ Interactive Payload Customization
- 🧩 Interactive Message Context
- 📥 Button Response Handling

### 🧱 MessageBuilder & AIRich

- 🧩 MessageBuilder API
- 🔘 Button & ButtonV2
- 🎠 Carousel Messages
- 🤖 AIRich Message Utilities
- 🛠️ MessageBuilder Helpers

### 🌐 HTML App

- 📄 HTML App Message Support
- 🚀 sendHtmlApp
- 🔍 checkHtmlApp
- 📦 HTML Document Helpers

### 🟢 Status & UPSWGC

- 📢 Group Status Message Support
- 🧩 groupStatusMessageV2
- 👥 Status Recipient List via statusJidList
- 🏷️ Group Status Metadata

### 📋 List Messages

- 📃 List Message Formats
- 🗂️ List Sections
- 📌 List Rows
- 🏷️ Row Titles & Descriptions
- ⚙️ Interactive List Payloads

### 🖼️ Media Handling

- 🖼️ Image Processing Utilities
- 🎞️ Video Message Preparation
- 🔊 Audio Message Preparation
- 📁 Document Message Preparation
- 🎭 Sticker Message Support
- ⬆️ Media Upload Utilities
- ⬇️ Media Download Utilities
- 🧪 MIME Type Handling
- 🗃️ Media Metadata
- 🖼️ Thumbnail Handling
- 🔓 Encrypted Media Download Utilities

### 👥 Group & Chat Utilities

- 👥 Group Metadata Retrieval
- 🪪 Participant Information
- 🔔 Participant Update Events
- ✏️ Group Subject & Description Utilities
- 🔗 Group Invite Information
- 💬 Chat Update Events
- 📇 Contact Update Events
- 🟢 Presence Updates
- 📨 Message Receipt Updates

### 🧰 Developer Utilities

- 📦 JavaScript ESM Support
- 🟦 TypeScript Definitions
- 🎧 Event-Based Architecture
- 🆔 JID Utilities
- 📝 Message Formatting Utilities
- 🔢 Binary Node Utilities
- 🧬 Protocol Buffer Integration
- 📜 Logger Integration
- 🔐 Custom Authentication State Integration

### 🛡️ Security & Protocol

- 🔒 End-to-End Encryption
- 🗝️ Signal Protocol Integration
- 📲 Device Identity Handling
- 🔏 Message Encryption Utilities
- 🌐 WebSocket Communication
- 🧱 Binary Node Encoding & Decoding
- 🧬 Protocol Buffer Serialization

---

> ⚠️ **Feature Notice:** Feature availability depends on the actual implementation in the installed version and WhatsApp compatibility. Beberapa fitur mungkin memerlukan payload khusus atau belum aktif di semua versi.

---

## Installation

Install Hyrox using npm:

    npm install hyrox@0.1.4

## Use Hyrox as "baileys"

Already using "baileys" in your project? No worries. Kamu nggak perlu langsung mengubah semua import di kode bot.

Add this to your `package.json`:

    {
      "dependencies": {
        "baileys": "npm:hyrox@0.1.4"
      }
    }

Then run:

    npm install

This installs Hyrox under the dependency name "baileys", allowing existing imports to remain unchanged when the APIs are compatible.

## Quick Start

    import makeWASocket from 'baileys'

    const sock = makeWASocket({
      auth: state,
      printQRInTerminal: false
    })

`state` is a placeholder for your configured authentication state. Sesuaikan dengan sistem session dan proses login pada project kamu.

## Sending a Message

    await sock.sendMessage(
      '1234567890@s.whatsapp.net',
      {
        text: 'Hello from Hyrox!'
      }
    )

Make sure the socket is connected and the destination JID is valid before sending messages.

## Interactive Messaging

Hyrox 0.1.4 expands interactive messaging with:

- MessageBuilder
- Button and ButtonV2
- Carousel
- AIRich utilities
- HTML App helpers
- Group Status support (UPSWGC)

### Example Imports

```js
import {
  MessageBuilder,
  Button,
  ButtonV2,
  Carousel,
  AIRich,
  MB,
  sendHtmlApp,
  checkHtmlApp
} from 'hyrox'
```

Payload structure and availability depend on the implementation and WhatsApp client compatibility.

**Note:** Not every interactive format is guaranteed to work on all WhatsApp clients.

## Compatibility

- **Runtime:** Node.js version compatible with the underlying Baileys release.
- **Module System:** JavaScript ESM.
- **WhatsApp:** Compatibility may change when WhatsApp updates its protocol.
- **Interactive Messages:** Availability depends on payload structure and client support.

Before upgrading or switching versions, test authentication, session reuse, message delivery, and the interactive features used by your bot.

## Development Philosophy

Hyrox follows a simple direction:

- Keep the connection foundation practical.
- Improve interactive messaging support.
- Maintain compatibility where possible.
- Make integration easier for existing bot projects.
- Build improvements through testing and development.

Small changes, better flexibility, continuous improvement.

## Credits & Acknowledgements

Hyrox is built upon the work and ideas shared by the open-source community.

- **WhiskeySockets** — Baileys foundation.
- **Itsliaaa** — Reference for interactive messaging implementation.

Special thanks to the original developers and contributors whose work helps the community build and customize WhatsApp bot projects.

Please respect the licenses and attribution requirements of the original projects.

## Disclaimer

Hyrox is an independent third-party fork. It is not officially affiliated with, endorsed by, or sponsored by WhatsApp or WhiskeySockets.

WhatsApp and related trademarks belong to their respective owners.

Use this package responsibly and follow applicable terms of service. Feature availability and compatibility are not guaranteed across all WhatsApp versions.

## License

Check the original repository's license and preserve all required copyright notices and attributions. The applicable license information should be included in the published package.

## Issues & Contributions

Found a bug or have an improvement idea?

When opening an issue, include:

- Hyrox version
- Node.js version
- Runtime environment
- Relevant error logs
- Steps to reproduce the issue

Clear reports make debugging easier and help improve the project.

---

<div align="center">

# HYROX

Built for WhatsApp bot development.

More flexibility. More possibilities.

</div>
