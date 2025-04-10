# Flipcard

A web component built with Lit for displaying interactive flipcard images with grid support. This package provides a custom element `<flipcard-viewer>` that can display and interact with grid-based flipcard images, supporting automatic orientation correction and responsive sizing.

## Features

- Grid-based image display with configurable rows and columns
- Interactive flip card animation
- Automatic image orientation correction (EXIF)
- Responsive sizing based on container dimensions
- IPFS gateway support
- Built with Lit for optimal performance

## Installation

```bash
npm install @dek-art/flipcard
# or
yarn add @dek-art/flipcard
```

## Import Options

The component can be imported in several ways depending on your use case:

### Option 1: Custom Element Usage (Recommended for most cases)
```javascript
// This will register the custom element automatically
import '@dek-art/flipcard';

// Use in HTML or templates
// <flipcard-viewer metadata-json="..." gateway-url="..."></flipcard-viewer>
```

### Option 2: Class Import (For advanced use cases)
```javascript
// Import the class directly
import { FlipcardViewer } from '@dek-art/flipcard';

// The class can be used for:
// - Extending the component
// - Type checking
// - Programmatic element creation
const element = new FlipcardViewer();
```

### Option 3: Default Import
```javascript
// Alternative way to import the class
import FlipCard from '@dek-art/flipcard';
```

Note: When using the component in frameworks like Vue, React, or Angular, you should use Option 1 (custom element usage) and ensure the component is properly registered in your framework's component system.

## Usage

The component will be automatically registered as a custom element `<flipcard-viewer>`. You can use it directly in your HTML:

```html
<flipcard-viewer
  metadata-json='{
    "image": "ipfs://QmExample...",
    "properties": {
      "display": {
        "rows": 2,
        "columns": 2
      }
    }
  }'
  gateway-url="https://www.ipfs.io/ipfs/"
></flipcard-viewer>
```

## Complete Example

```html
<!DOCTYPE html>
<html>
<head>
  <script type="module">
    import '@dek-art/flipcard';
  </script>
</head>
<body>
  <flipcard-viewer
    metadata-json='{
      "image": "ipfs://QmExample...",
      "properties": {
        "display": {
          "rows": 2,
          "columns": 2
        }
      }
    }'
    gateway-url="https://www.ipfs.io/ipfs/"
  ></flipcard-viewer>
</body>
</html>
```

## Properties

| Property | Type | Description | Default |
|----------|------|-------------|---------|
| `metadata-json` | String | JSON string containing image metadata and display properties | `""` |
| `gateway-url` | String | Base URL for the IPFS gateway | `"https://www.ipfs.io/ipfs/"` |

### Metadata JSON Format

```json
{
  "image": "ipfs://QmHash...",
  "properties": {
    "display": {
      "rows": 2,
      "columns": 2
    }
  }
}
```

## Browser Support

- Chrome/Edge (latest)
- Firefox (latest)
- Safari (latest)
- Safari iOS (13.4+)

## Development

```bash
# Install dependencies
yarn install

# Start development server
yarn start

# Run tests
yarn test

# Build for production
yarn build
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## Acknowledgments

- Built with [Lit](https://lit.dev/)
- EXIF data parsing with [exifr](https://github.com/MikeKovarik/exifr)
