# Omnissiah Tools

Swift utilities and CLI tools for the Omnissiah ecosystem. Clean, efficient, secure.

## 🎯 Purpose

Shared utilities used across the Omnissiah projects — from iOS apps to MCP servers.

## 📦 Tools

| Tool | Language | Purpose |
|------|----------|---------|
| `omni-log` | Swift | Structured logging with security audit trails |
| `omni-secure` | Swift | Input validation, sanitization, crypto helpers |
| `omni-net` | Swift | Network layer with retry, caching, rate limiting |
| `omni-cli` | Swift | CLI framework for internal tools |

## 🚀 Quick Start

### Swift Package Manager

```swift
dependencies: [
    .package(url: "https://github.com/machineaccess1010-sketch/omnissiah-tools.git", from: "1.0.0")
]
```

### CLI Installation

```bash
brew tap machineaccess1010-sketch/omnissiah
brew install omnissiah-tools
```

## 🛠️ Usage Examples

### Structured Logging
```swift
import OmniLog

let logger = Logger("security")
logger.security("MCP tool executed", metadata: [
    "tool": "blender.render",
    "user": "controller",
    "duration_ms": 120
])
```

### Input Validation
```swift
import OmniSecure

let validator = Validator<String>
    .nonEmpty()
    .maxLength(100)
    .matches(/^[a-zA-Z0-9_]+$/)

do {
    let validated = try validator.validate(userInput)
} catch {
    // Validation failed, log security event
}
```

### Network with Caching
```swift
import OmniNet

let client = HTTPClient()
    .withRetry(maxAttempts: 3)
    .withCache(ttl: 3600)
    .withRateLimit(requestsPerMinute: 60)

let response = try await client.get("https://api.example.com/data")
```

## 🔒 Security Features

- **Audit logging** — All operations logged with tamper-evident hashes
- **Input validation** — Type-safe, schema-based validation
- **Secure defaults** — Encryption, timeouts, sanitization built-in
- **Zero dependencies** — Minimal attack surface

## 🧪 Testing

```bash
swift test

# With coverage
swift test --enable-code-coverage
```

## 📁 Project Structure

```
Sources/
├── OmniLog/          # Structured logging
├── OmniSecure/       # Security utilities
├── OmniNet/          # Network layer
└── OmniCLI/          # CLI framework

Tests/
├── OmniLogTests/
├── OmniSecureTests/
├── OmniNetTests/
└── OmniCLITests/
```

## 🤝 Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

All code must:
- Pass SwiftLint checks
- Have 80%+ test coverage
- Include security review for crypto/auth code
- Be documented with DocC

## 📜 License

MIT License — see [LICENSE](LICENSE)

## 🔗 Related

- [Omnissiah MCP](https://github.com/machineaccess1010-sketch/omnissiah-mcp) — MCP servers
- [Soul Chat](https://github.com/machineaccess1010-sketch/soul-chat) — iOS chat app

---

**Built with Swift** | **Efficient by design** | **Secure by default**
