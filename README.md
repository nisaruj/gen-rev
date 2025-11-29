# gen-rev

Vibe coded a command-line utility for generating reverse shell payloads that I usually use.

## Features

- **Multi-Language Support**: Generates reverse shell payloads in Bash, Python, Netcat, and PowerShell
- **Interactive IP Selection**: Automatically detects and lists available network interfaces for easy IP selection
- **Simple CLI**: Minimal command-line interface with intuitive usage
- **Colored Output**: Enhanced readability with color-coded sections and formatting

## Installation


### Build from Source
```bash
cargo build --release
```

The compiled binary will be available at `target/release/rev-gen`.

## Usage

```bash
rev-gen <PORT> [OPTIONS]
```

### Arguments
- `<PORT>`: The listening port for the reverse shell connection (required)

### Options
- `-i, --ip <IP>`: Specify the listener IP address (if not provided, you'll be prompted to select one)
- `--all`: Include all network interfaces in selection (default: true)

### Examples

```bash
# Interactive mode - select IP from available interfaces
rev-gen 4444

# Specify IP directly
rev-gen 4444 --ip 192.168.1.100

# Different port
rev-gen 8080 --ip 10.0.0.5
```

## Generated Payloads

The tool generates payloads in the following languages:

1. **Bash**: Direct bash reverse shell
2. **Python3**: Interactive Python reverse shell with PTY support
3. **Python3 (Base64)**: Base64-encoded Python payload
4. **Netcat**: Netcat-based reverse shell (if available)
5. **PowerShell**: Windows PowerShell reverse shell

## Security Notice

This tool is intended for authorized security testing only. Unauthorized access to computer systems is illegal. Always ensure you have proper authorization before conducting security tests.

## License

MIT
