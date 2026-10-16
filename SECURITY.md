# Security and privacy

**Documentation-only repository.** No original conversation exports, production databases, logs, hostnames, internal paths, IP addresses, credentials, API tokens or private memory records belong here.

## Safe-use rules
- Use synthetic datasets and non-sensitive local paths.
- Bind development services to loopback unless protected by deliberate authentication, network policy and TLS.
- Never publish FalkorDB, SQLite files or MCP endpoints directly to the Internet.
- Keep secrets in local environment or a secrets manager, never committed to Git.
- Sanitize error output, logs, prompts and retrieved records.
- Use dependency pinning and security scanning before any executable example is deployed.
- Do not treat a public example as a production-hardened configuration.

## Reporting
If you find a secret or sensitive record, avoid posting it in a public issue. Contact the repository maintainer privately through GitHub.
