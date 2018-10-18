## "MFA the Right Way: One Time Passwords with PyOTP" by Collin Stedman

Negligence isn't usually the reason security fails;
a complex combination of small choices is often to blame.
Somebody will eventually leak password information, however.


## Multi-factor authentication

Several pieces of (ideally) independent information that would be difficult to compromise simultaneously.
An OTP often uses asymmetric encryption and time-sensitivity to generate a new code each time authentication occurs.
A common implementation is a token-based on time password (OTP).
A token stored in the client and the server is hashed along with a message to produce unique output code.


## Types of OTPs

HMAC-based OTPs (HOTP) use a simple counter as the hash message, but this can get out of sync fairly easily.
It often uses a window of values on the server-side to counteract this.
HOTP often uses SHA-1, but remains fairly secure because HOTP relies on the pattern of the input to output mapping.
It would still be computationally expensive to crack.

Time-based OTPs (TOTP) instead use timestamps which generally stay in sync if the time on the devices is in sync.
This still uses a window to account for lag.
It needs a device to be powered so the time is known.


## PyOTP

PyOTP makes it easy to set up multi-factor authentication in Django using views and form validation.


## Miscellaneous

`qrious` for QR code generation!
