# CVE detection scripts

A collection of scripts to help assess systems for specific Common Vulnerabilities and Exposures (CVEs). Each script is named for the CVE it covers.

## Available scripts

| CVE | Script | Scope |
| --- | --- | --- |
| CVE-2026-98432 | [`check-cve-2026-98432-use-after-free-issue.sh`](check-cve-2026-98432-use-after-free-issue.sh) | Linux kernel IPv4 use-after-free; checks package evidence for selected Debian kernels and provides guidance for other systems. |

## Usage

Review a script before running it on the system you want to assess. For example:

```bash
bash check-cve-2026-98432-use-after-free-issue.sh
```

The CVE-2026-98432 script is read-only: it does not install updates, refresh package metadata, change settings, or reboot. It may suggest update commands, but does not run them. Package-manager results depend on the locally available metadata. In a container, assess the host kernel on the host itself.

For that script, exit codes are `0` for fixed by package-version evidence, `1` for vulnerable by package-version evidence, and `2` for unknown or advisory-only results. Other scripts may use different conventions; consult each script's documentation.

## Limitations

These scripts assist assessment; they are not a substitute for current vendor advisories. An unknown result does not mean a system is safe. Distribution backports, custom kernels, live patches, stale metadata, and runtime environment can affect results. Confirm the running software version and relevant vendor guidance, and review any suggested changes before applying them.

## License

See [LICENSE](LICENSE).
