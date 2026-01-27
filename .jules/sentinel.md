## 2025-01-27 - [Unimplemented Localization Strings]
**Vulnerability:** Ambiguity in security whitelisting due to unused code artifacts.
**Learning:** The codebase contained localization strings for `taxonomy` and `author` visibility types that were NOT implemented in the frontend or backend logic. This created confusion during security review, where it appeared that whitelisting valid types might accidentally exclude these "features".
**Prevention:** When creating security whitelists, verify actual implementation of features, not just existence of strings or constants. However, in this case, adding them to the whitelist was the safer path to avoid regression in case of hidden usage or future activation.
