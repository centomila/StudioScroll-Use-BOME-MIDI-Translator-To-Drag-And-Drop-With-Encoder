# StudioScroll

**StudioScroll** is a _BOME Midi Translator Pro_ project inspired by [Bitwig Connect](https://www.bitwig.com/connect/), allowing precise drag-and-drop control using a MIDI encoder. It works seamlessly with any application like DAWs or VST plugin without requiring additional configuration outside of Bome. You can also use it on Paint! 🎨

---

## 🌟 Key Features
- Control **faders**, **knobs**, **clips**, and **automation** with precision.
- Works with **any application** supporting mouse drag-and-drop.
- Perfect for DAWs and creative software.

---

## 🛠️ Requirements
- **Bome MIDI Translator Pro** ([Download](https://www.bome.com/products/miditranslator)):
  - Paid app, but the trial works for 20 minutes at a time without limitations.
  - If purchasing, search for coupons as they are often available.
- **Operating System**: Windows or macOS.
- **MIDI Controller**:
  - Must send **3FH/41H encoder messages**.
  - Tested with the **Midi Fighter Twister**.
- **Virtual MIDI Ports**:
  - Ensure at least 2 are enabled in Bome settings.
- **Optional Input**: Works with the volume wheel of your PC keyboard (vertical scrolling only, disabled by default).

---

## 🔧 Configuration Instructions

### 1. Set Up Virtual MIDI Ports
- Go to **View > Settings > Virtual MIDI Ports**.
- Set the **Number of Virtual Ports** to **2 Ports**.

### 2. Configure MIDI Input and Output
- In **Project Properties**:
  - Set **Controller MIDI IN** to your MIDI controller.
  - Set **Controller MIDI OUT** to the same controller.

### 3. Configure MIDI Messages
- In the preset **[0] MIDI Encoders**:
  - Select **[1] UP**.
  - Enable **Capture MIDI**, move your encoder for the UP action, and select the detected MIDI message.
  - Repeat for DOWN, LEFT, and RIGHT.

### 4. Adjust Movement Sensitivity
- In **[3] INIT Variables > [1]Set Global Vars**, adjust:
  ```plaintext
  // Movement Speed
  gp=1  // Positive movement
  gn=-1 // Negative movement
  ```
  Default is 1 pixel per step. Increase for faster movement.

---

## ⚠️ Limitations
- StudioScroll **does not send MIDI mappings**. If you move your mouse away from the controlled element, it stops controlling it.
- Horizontal scrolling requires two separate encoders.
- Works only with encoders; knobs and faders are not ideal.

---

## 🚀 Getting Started
1. Set up your MIDI ports and messages.
2. Place your mouse over a fader, knob, or element.
3. Turn the encoder to control it. No additional configuration is needed in your DAW or VST.

---

## 📝 Changelog

**0.5**
- Global Variables:
  - Change "gp" and "gn" values to adjust relative mouse movement.
    - Default: gn = -1, gp = 1 (values in pixels, integers only).
  - Change "gs" to adjust the delay (in milliseconds) after the last encoder touch.
    - Default: gs = 350 (values in milliseconds, integers only).

**0.4**
- Added support for horizontal drag and drop.
- Separated presets for easier management.

**0.3**
- Added an alternative input method via keystrokes.

**0.2**
- Fixed accidental double clicks by adding an extra variable on release.
- Increased the release delay to 500ms to prevent double clicks during slow movements.

**0.1**
- Initial prototype.

---