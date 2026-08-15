# Keyman Web Bookmarklet

The **Keyman Bookmarklet** allows users to load custom multi-language keyboard layouts on virtually any web page. By adding a specialized bookmark to a browser's bookmarks bar, users can inject the JavaScript-based KeymanWeb Engine directly into their current active tab.

## Features
* **Zero Installation:** Works purely via browser JavaScript injection without requiring administrative privileges or system-level installer software.
* **Universal Compatibility:** Supported across major desktop web browsers including Google Chrome, Mozilla Firefox, Microsoft Edge, and Apple Safari.
* **Cloud Integration:** Dynamically pulls verified keyboard layouts from the Keyman Cloud Engine Repository.
* **On-Screen Keyboard:** Provides an interactive visual interface to assist with typing complex scripts, layouts, and hidden diacritics.

## Installation

To install a specific keyboard on a local web browser, users follow these core steps:

1. Open your browser and ensure the **Bookmarks Toolbar** or **Favorites Bar** is visible (`Ctrl+Shift+B` or `Cmd+Shift+B`).
2. Navigate to your desired target language on the official site.
3. Locate the generated **Keyman Bookmarklet** button for that language.
4. **Click and drag** the button directly onto your browser's Bookmarks Toolbar.

## How to Use

1. Navigate to any website containing text inputs (e.g., a search engine or online form).
2. Click the saved **Keyman Keyboard bookmark** from your toolbar.
3. Wait 1–2 seconds for the KeymanWeb layout scripts to initialize on the page.
4. Click inside any text box or input field.
5. The interactive Keyman UI will appear, instantly mapping your physical hardware keyboard to the chosen language layout.

## Technical Snippet (Bookmarklet Code)

If you are creating custom bookmarklets or testing deployment scripts, the layout relies on a minimized `javascript:` URI scheme snippet. The underlying loader injects the script directly into the page DOM:

```javascript
javascript:(function(){
  var el = document.createElement('script');
  el.src = 'https://r.keymanweb.com/code/bookmarklet.js?keyboard=your_keyboard_id&language=your_lang_id';
  document.body.appendChild(el);
})();
```

### Script Parameter Configurations
* **`keyboard`**: The specific ID of the keyboard layout fetched from the open-source Keyman Keyboards Repository on GitHub (e.g., `khmer_angkor`, `tamil_99`).
* **`language`**: The standard BCP 47 or ISO 639-3 language code associated with the layout typing rules.

## Known Development Limitations
* **Content Security Policies (CSP):** Heavily secured web applications (such as enterprise software or online banking portals) explicitly block third-party script injections via strict CSP headers, preventing the bookmarklet from executing on those pages.
* **Isolated Iframes:** Inputs nested deep inside isolated cross-origin `<iframe>` elements cannot be manipulated by the parent page's injected script logic.

## Feedback and Support

The codebase for the layout framework is entirely open-source under the Keyman App Organization on GitHub. 
* **Issues:** Report loader bugs or suggest features on the primary Keyman Issue Tracker on GitHub.
* **Discussions:** Ask technical usage questions or share community layouts on the SIL Software Community Forum.
