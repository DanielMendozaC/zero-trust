#  Zero Trust AI Agent

An AI agent implementation using Claude with enforced Zero Trust architecture for file operations.

## Features

- **Zero Trust Framework**: Every action is verified against policies before execution
- **Policy Engine**: JSON based configuration for granular access control
- **Audit Logging**: Complete JSON logs of all attempted operations
- **Input Validation**: Path traversal and injection attack prevention
- **Rate Limiting**: Configurable request throttling per function
- **Risk Scoring**: Risk assessment with threat detection
- **Streamlit UI**: Interactive web interface with security visualization

## Quick Start

### Installation
```bash
pip install anthropic streamlit python-dotenv
```

### Setup
1. Create `.env` file with your API key:
   ```
   ANTHROPIC_API_KEY=your-key-here
   ```

2. Review `policies.json` to define what operations are allowed

### Run

**Interactive web version:**
```bash
streamlit run streamlit_app_v2.py
```

## How It Works

1. User makes a request
2. Claude determines what action is needed
3. Zero Trust security checks run:
   - Input validation
   - Rate limiting
   - Policy verification
   - Risk assessment
4. Action is logged and executed (or blocked)
5. Result returned to user

## Files

- `main.py` - Core Zero Trust implementation
- `streamlit_app_v2.py` - Enhanced UI with full security features
- `policies.json` - Access control policies
- `audit_log.txt` - Complete action audit trail

## Security Best Practices

**Never commit credentials.txt to version control**  
- Use environment variables for sensitive data
- Rotate credentials regularly
- Review audit logs for suspicious patterns

## Configuration

Edit `policies.json` to control what Claude can do:
```json
{
  "read_file": { "allowed": true },
  "write_file": { "allowed": true },
  "delete_file": { "allowed": false }
}
```

## License

MIT
