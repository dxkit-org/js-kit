# DXKit JS Kit

> **Modern TypeScript utility library with tree-shaking support** - Comprehensive collection of array, string, number, sleep, and time utilities for JavaScript and TypeScript projects.

[![npm version](https://badge.fury.io/js/@dxkit-org/js-kit.svg)](https://www.npmjs.com/package/@dxkit-org/js-kit)
[![TypeScript](https://img.shields.io/badge/TypeScript-Ready-blue.svg)](https://www.typescriptlang.org/)
[![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)
[![Tree Shakable](https://img.shields.io/badge/Tree--Shakable-✓-brightgreen.svg)](https://webpack.js.org/guides/tree-shaking/)

A collection of JavaScript/TypeScript utility functions for modern development.

## 🌐 Environment Compatibility

This library is designed to work across multiple JavaScript environments:

- **✅ `@dxkit-org/js-kit`** - Universal utilities that work in **Node.js**, **Browser**, and **Web Workers**
- ** Individual imports** - `@dxkit-org/js-kit/module/function` for maximum tree-shaking

## Features

- 🚀 **TypeScript Support** - Full TypeScript support with type definitions
- 📦 **Tree Shakable** - Import only what you need
- 🧪 **Well Tested** - Comprehensive test coverage
- 📖 **Well Documented** - JSDoc comments for all functions
- 🔧 **Modern Build** - Built with tsup for optimal bundling
- 💡 **Excellent IDE Support** - Full auto-completion and IntelliSense support
- 🌐 **Cross-Platform** - Works in Node.js, browsers, and web workers

## Installation

```bash
npm install @dxkit-org/js-kit
```

**Alternative package managers:**

```bash
# Yarn
yarn add @dxkit-org/js-kit

# pnpm
pnpm add @dxkit-org/js-kit

# Bun
bun add @dxkit-org/js-kit
```

## Usage

### Universal Modules

Import universal modules that work in **Node.js**, **Browser**, and **Web Workers**:

```typescript
import {
  chunk,
  capitalize,
  clamp,
  sleep,
  convertToSeconds,
} from "@dxkit-org/js-kit"

// Array utilities
const chunkedArray = chunk([1, 2, 3, 4, 5], 2)
// Result: [[1, 2], [3, 4], [5]]

// String utilities
const capitalizedString = capitalize("hello world")
// Result: "Hello world"

// Number utilities
const clampedNumber = clamp(15, 0, 10)
// Result: 10

// Sleep utilities
await sleep({ seconds: 2, milliseconds: 500 }) // Sleep for 2.5 seconds

// Time utilities
const seconds = convertToSeconds({ minutes: 5, seconds: 30 })
// Result: 330 (seconds)
```

### Tree-shaking Support

You can also import individual functions for optimal tree-shaking:

```typescript
// Universal utilities - individual imports
import { chunk } from "@dxkit-org/js-kit/array/chunk"
import { capitalize } from "@dxkit-org/js-kit/string/capitalize"
import { clamp } from "@dxkit-org/js-kit/number/clamp"
import { sleep } from "@dxkit-org/js-kit/sleep/sleep"
import { convertToSeconds } from "@dxkit-org/js-kit/time/time"

// Universal bundle (recommended)
import { chunk, capitalize, clamp } from "@dxkit-org/js-kit"
```

## 📋 Available Modules

### ✅ Universal Modules (Node.js + Browser + Web Workers)

| Module              | Functions                                                     | Description                                  |
| ------------------- | ------------------------------------------------------------- | -------------------------------------------- |
| `array/chunk`       | `chunk`                                                       | Split arrays into chunks of specified size   |
| `string/capitalize` | `capitalize`, `capitalizeWords`                               | String capitalization utilities              |
| `number/clamp`      | `clamp`, `inRange`                                            | Number range utilities                       |
| `sleep/sleep`       | `sleep`                                                       | Promise-based sleep with multiple time units |
| `time/time`         | `convertToSeconds`                                            | Time conversion utilities                    |
| `utils/environment` | `isNodeEnvironment`, `isBrowserEnvironment`, `getEnvironment` | Environment detection                        |

## TypeScript Configuration

For optimal compatibility with this package, ensure your `tsconfig.json` uses modern module resolution:

```json
{
  "compilerOptions": {
    "moduleResolution": "bundler", // or "node16"/"nodenext"
    "module": "ESNext", // or "Node16"
    "esModuleInterop": true,
    "allowSyntheticDefaultImports": true,
    "skipLibCheck": true
  }
}
```

### Troubleshooting Import Issues

If you encounter module resolution errors like:

```
Cannot find module 'advanced-js-kit/string/capitalize' or its corresponding type declarations
```

Try these solutions:

1. **Update your TypeScript configuration** to use modern module resolution (see above)
2. **Ensure you're using a recent Node.js version** (16+ recommended)
3. **Copy the example configuration** from `example-tsconfig-for-consumers.json` in this package
4. **As a workaround**, you can import directly from the dist folder:
   ```typescript
   import { capitalize } from "advanced-js-kit/dist/string/capitalize.js"
   ```

### IDE Support

This package provides excellent IDE support with:

- **Auto-completion** for all functions and their parameters
- **Type checking** with full TypeScript support
- **JSDoc documentation** shown in hover tooltips
- **Auto-import** suggestions when typing function names

## API Reference

### 📚 Package Documentation

For comprehensive documentation with examples, advanced usage patterns, and best practices, see the individual package documentation:

- **[🔢 Array Utilities](./src/array/array.md)** - Array manipulation and chunking utilities
- **[🔢 Number Utilities](./src/number/number.md)** - Number clamping and range validation
- **[⏰ Sleep Utilities](./src/sleep/sleep.md)** - Advanced sleep and timing functions
- **[📝 String Utilities](./src/string/string.md)** - String manipulation and formatting
- **[⏰ Time Utilities](./src/time/time.md)** - Time conversion and duration utilities

### Quick Reference

#### Array Utilities

- `chunk<T>(array: T[], size: number): T[][]` - Splits an array into chunks of a specified size

#### String Utilities

- `capitalize(str: string): string` - Capitalizes the first letter of a string
- `capitalizeWords(str: string): string` - Capitalizes the first letter of each word

#### Number Utilities

- `clamp(number: number, lower: number, upper: number): number` - Clamps a number within bounds
- `inRange(number: number, lower: number, upper: number): boolean` - Checks if number is in range

#### Sleep Utilities

- `sleep(params: TSleepParams): Promise<void>` - Advanced sleep with flexible options
- `sleepMs(ms: number): Promise<void>` - Sleep for milliseconds
- `sleepSeconds(seconds: number): Promise<void>` - Sleep for seconds
- `sleepMinutes(minutes: number): Promise<void>` - Sleep for minutes
- `sleepUntil(unixTimestamp: number): Promise<void>` - Sleep until timestamp

## Development

```bash
# Install dependencies
npm install

# Build the project
npm run build

# Watch mode for development
npm run dev

# Type checking
npm run type-check

# Run tests
npm run test
```

## License

MIT
