# Setup MFA (Multi-Factor Authentication)

## Definition
MFA adds an extra layer of security by requiring a second form of verification like OTP from an authenticator app.

## Use Case
- Protect root account
- Enforce MFA for IAM users logging in

## Steps

### AWS Console
1. Go to IAM → Users → Security credentials
2. Click "Manage MFA"
3. Choose Virtual MFA device (e.g., Google Authenticator)
4. Scan QR code
5. Enter 2 consecutive OTPs to activate
