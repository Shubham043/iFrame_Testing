# Iframe Testing Repository

This project is a simple test environment designed to experiment with, debug, and verify `<iframe>` behaviors, security policies, and cross-origin communication.

## Features

- Test cross-origin resource sharing (CORS) and embedding permissions.
- Experiment with `sandbox` attributes and security restrictions.
- Test `postMessage` API communication between the parent window and the iframe.
- Verify responsive scaling and styling inside different container sizes.

## Project Structure

```text
├── index.html       # Parent window containing the iframe
├── iframe-content.html  # Sample page loaded inside the iframe
├── script.js        # Logic for postMessage communication and controls
└── style.css        # Basic styling for layout visualization
```

## Getting Started

### Prerequisites

You need a basic local web server to test cross-origin or standard iframe rules properly. 
- [Node.js](https://nodejs.org) or a simple extension like **Live Server** in VS Code.

### Installation & Running

1. Clone the repository:
   ```bash
   git clone https://github.com
   ```
2. Navigate to the project folder:
   ```bash
   cd iframe-testing
   ```
3. Open the project using a local server (e.g., run `npx serve` or open `index.html` via Live Server).

## Usage Examples

### Adding a Sandbox Attribute
To restrict capabilities inside the iframe, configure the tag in `index.html`:
```html
<iframe src="iframe-content.html" sandbox="allow-scripts allow-same-origin"></iframe>
```

### Sending Messages via `postMessage`
- **Parent to Child:**
  ```javascript
  const iframe = document.querySelector('iframe');
  iframe.contentWindow.postMessage('Hello from parent!', '*');
  ```
- **Child to Parent:**
  ```javascript
  window.parent.postMessage('Hello from child!', '*');
  ```

## Contributing

Pull requests are welcome! For major changes, please open an issue first to discuss what you would like to change.

## License

This project is open-source and available under the [MIT License](LICENSE).
