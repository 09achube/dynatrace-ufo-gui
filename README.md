# dynatrace-ufo-gui
A self-contained HTML/Javascript GUI for the Dynatrace UFO to enable easy customization and visualization.

Full-disclosure, this was primarily created with Claude and I'm not a professional developer so I can't fully vouch for the efficiency or security of this code.  This should not be used in a production environment.

# UFO Controller Interfaces

Two browser-based controller GUIs for managing and visualizing the Dynatrace UFO LED display over Wi-Fi.

## Files

### `ufo-controller.html` (Desktop)
Full-featured desktop controller with a three-column layout optimized for 14"+ screens.

**Layout:**
- Left panel: LED ring previews + logo control
- Center: Top ring LED segment builder + animations (whirl, morph)
- Right: Bottom ring LED segment builder + animations
- Full width: Quick presets grid

**Best for:**
- Laptop or desktop browser
- Detailed LED configuration
- Monitoring and testing with multiple controls visible simultaneously

### `ufo-controller-mobile.html` (Mobile)
Touch-friendly interface optimized for phones in portrait mode.

**Layout:**
- Sticky header with IP connection bar
- Single-column card stack
- Responsive presets: 2 columns on phone, auto-fill grid on tablets/desktop
- Larger touch targets (44px minimum)
- Mobile-safe keyboard attributes on IP input

**Best for:**
- Smartphone browsers (iOS Safari, Android Chrome)
- Quick LED control from anywhere
- Field troubleshooting or CI/CD monitoring at a glance

**Deployable to UFO firmware:**
- Copy: `data/index-mobile.html`
- Access on UFO: `http://<ufo-ip>/index-mobile.html`

## How to use

Download the respective .html controller to the device you want to control the UFO from and open in a browser.

### 1. Connect to UFO

Enter the UFO's IP address in the top-left field and click **Connect**.

### 2. Control the LEDs

**Logo LED:** On / Off / Default buttons or set individual LED color + brightness.

**Top & Bottom Rings:** 
- Add LED segments: set position (0-14), count (1-15), pick a color, tap **+ Add**
- Animations: toggle **Whirl** (spinning) or **Morph** (pulsing) with speed/direction controls
- Background color: pick a base color for unlit LEDs
- Send: tap **Send Top Ring** or **Send Bottom Ring** to push to UFO

**Quick Presets:** Tap a preset button to apply a pre-configured scene (Red Alert, Rainbow Spin, Deploy Success, etc.) to both rings at once.

### 3. Monitor Status

The status bar shows:
- ✓ Sent: command successful
- ⚠ / ✗ Error: connection failed, timeout, or invalid input

## Features

### Common to Both
- Real-time LED ring preview (SVG visualization)
- API endpoint display (see exact REST call being sent)
- 15-position LED rings with full RGB color support
- Animations: Whirl (rotating pattern) + Morph (pulsing effect)
- 13 quick preset configurations
- Stateless design—no server required beyond the UFO itself

### Desktop Only
- Multi-column layout for side-by-side editing
- Larger SVG ring previews (160px)

### Mobile Only
- Optimized touch spacing (44px minimum tap targets)
- Mobile keyboard safeguards (disable autocorrect/autocapitalize on IP field)
- Responsive grid: 2 columns on phone → auto-fill on wide screens
- Smaller SVG ring previews (150px max)
- Horizontal scroll preset buttons on very small screens

**Version:** 2.0  
**Last Updated:** 2026-07-20
