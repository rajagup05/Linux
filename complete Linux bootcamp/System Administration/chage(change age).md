
## chage(change age)

The chage command in Linux modifies user password expiry and account aging details. As the root user, you can set maximum password validity periods, force immediate password changes on next login, and establish account expiration dates to maintain security.

usage and examples: 

- View aging details: `sudo chage -l username`
- Force a password change on next login: `sudo chage -d 0 username`
- Set password to expire every 90 days: `sudo chage -M 90 username`
- Disable password expiration: `sudo chage -M -1 username`
- Set an account expiration date (e.g., YYYY-MM-DD): `sudo chage -E 2026-12-31 username`
