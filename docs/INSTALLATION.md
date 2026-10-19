# Install Multiagentic Platform 1.1.25

[Download the Windows installer](https://github.com/michelegiletto-beep/multiagentic-platform/releases/download/v1.1.25/MultiagenticPlatform-Setup-1.1.25.exe)

The application connects to a compatible broker account supplied by its user. Installation starts with an empty Agents Hub and does not start automatic trading. Read the [binary licence](releases/1.1.25/LICENSE.txt), [known limitations](releases/1.1.25/KNOWN-LIMITATIONS.txt) and the supplied [Italian first-start guide](releases/1.1.25/START-HERE.txt).

## Requirements and file verification

Use Windows 10 or 11 x64 with Microsoft Edge, .NET Framework 4.8 and Windows PowerShell. Node.js is included. No Python, GPU, OpenAI key or previous application installation is required. Internet access and personal broker API credentials are needed when connecting an account.

The installer is `MultiagenticPlatform-Setup-1.1.25.exe`, **84,921,344 bytes**. Its SHA-256 is:

```text
0fbafa46452a4c9bac3a53c395d778ec50c4312f82119cada7078d25ec9e608b
```

In the download directory, Windows PowerShell can calculate the file's hash:

```powershell
Get-FileHash -Algorithm SHA256 -LiteralPath .\MultiagenticPlatform-Setup-1.1.25.exe
```

Compare the result with the published value. The final installer is **Authenticode `NotSigned`**: it has no publisher certificate. Do not disable system protections to bypass an alert. The [release record](releases/1.1.25/README.md) identifies the checked package and verification scope.

## Installation and first start

1. Run the verified installer under your Windows user. It is a per-user installation; an administrator request is not expected.
2. The application installs to `%LOCALAPPDATA%\Programs\Multiagentic Platform\1.1.25`, with versioned Desktop and Start-menu shortcuts.
3. Start the application and create an agent in the Agents Hub. No agents, accounts or orders are preconfigured.
4. To inspect the interface before connecting an account, select **Apri senza collegare il conto** and, if shown, **Continua come osservatore**. Observer mode does not connect a broker, provide verified live quotes or authorise orders.

## Connect your own broker account

Broker forms initially select **Conto reale**. Choose Capital.com, IG CFD or OANDA and supply the API credentials for your own account and selected environment. Capital.com uses an identifier/email, API key and API password; OANDA uses an account ID and API token; IG CFD uses the credentials required for its API access. A broker-provided demo account can be selected explicitly with its corresponding credentials.

Verify the connection and confirm it yourself. Do not send credentials or private account information to the project. Connecting an account and enabling an operational strategy require deliberate user action. Check the provider, quote freshness, funds, orders and positions before enabling an operational workflow.

Capital.com has documented live observations with unresolved freshness, fallback and timeout findings. IG CFD and OANDA have mock-test evidence; full live qualification is not established. Release 1.1.25 does not claim to resolve those findings. Consult [KNOWN-LIMITATIONS.txt](releases/1.1.25/KNOWN-LIMITATIONS.txt).

## Local data, updates and removal

Public-distribution user data is separate from the program at `%LOCALAPPDATA%\Multiagentic Platform\data\v1`. Existing personal profiles are not imported automatically. Stored credentials use the application's Windows protection mechanism. Export your operational profile from the application before migration; avoid manually deleting its data directories.

Exit through **Esci e arresta i servizi locali**, then uninstall through Windows Settings > Apps or the version's `Uninstall.exe`. Uninstall removes the program, shortcuts and registration while retaining separate local user data. It does not close broker orders or positions. Removing local data and credentials requires a separate user decision.

If another version is already running, close it completely before starting this one; the local port may be occupied. For support, provide the version, error and diagnostic information with account details and credentials removed.
