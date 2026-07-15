# Squishy — Stack & Squish! 🫧

Squishy is a vibrant jelly-bubble stacking game built as an installable Progressive Web App (PWA). This project serves as a showcase for modular game design, utilizing the core engine developed for my previous projects while introducing a completely new visual identity.

**[Play It Live](https://yofranky.github.io/squishy-pwa/)**

---

## The Experience

The game centers on a grid-based stacking mechanic where every piece is reimagined as a soft, animated jelly bubble. The goal is to stack and clear lines, but with a unique visual flair:

* **Interactive Animation:** Each bubble features eyes that track your touch across the screen. When idle, the bubbles perform a continuous "wobble" and bounce whenever they lock into place.
* **Accessibility Features:** Despite the visual complexity, the game remains fully accessible. A "Reduce Motion" mode disables the wobble and bounce while maintaining the eye-tracking feature. It also includes an Okabe-Ito colorblind-safe palette, high-contrast settings, and toggleable haptics.
* **Intuitive Controls:** Designed for mobile first, the interface is large and responsive, ensuring a comfortable experience on any device.

## The Development Process

Like my previous work, this project was built through an AI-assisted development workflow. My role as the Technical Program Manager and developer was to take the core engine—which governs collision, scoring, and logic—and successfully layer a new visual engine on top of it.

By leveraging my children as my core testing team, I was able to refine the feel of the "jelly" physics and ensure the eye-tracking responsiveness met their expectations for fun. This iterative process allowed me to maintain the BKAOS standard of quality while learning how to effectively repurpose modular code across different projects.

## Why a PWA?

I prioritized the PWA model to ensure the game is immediately available to my family and users without the friction of traditional app stores.

* **Zero-Friction Access:** Users can launch the game via a web link. There are no accounts to manage and no download queues.
* **Rapid Updates:** This delivery method allows me to iterate on the game mechanics and visual animations and deploy those updates instantly.
* **Privacy and Performance:** The game contains no trackers, ad SDKs, or external font dependencies. It is built entirely with vanilla HTML, CSS, and JavaScript, creating a lightweight experience that remains fully functional offline.

## Technical Implementation

Squishy relies on the same robust technical foundation as my previous PWA titles, using the Canvas API for all rendering and the Web Audio and Vibration APIs for feedback.

A key technical challenge was decoupling the visual rendering from the game logic. I updated the shared rendering function (`drawBlock`) to map game grid coordinates to the new jelly-bubble assets. Additionally, I implemented coordinate transformation to map screen-space touch data into canvas-internal pixel space, which allows the "eyes" of the bubbles to follow a player's finger with precision regardless of screen scaling or device resolution.

## Deployment and Local Use

This project is hosted via GitHub Pages and is fully installable as a native-feeling app.

1. **Mobile:** Navigate to the game link in your browser, then select "Add to Home Screen" from your browser’s menu.
2. **Desktop:** Select the "Install" icon in your browser’s address bar.

For those interested in the source code, you can run the project locally by executing `npx serve .` in your terminal. Note that a local server is required to trigger the service worker and offline functionality.

---

*Squishy is a BKAOS project.*
