# Prowlarr

Prowlarr is exposed through the `prowlarr` NodePort Service on port `30696`.
HAProxy sends requests with the hostname `prowlarr.styxut.net`.

## Allowed hostname

Prowlarr's runtime host allowlist is stored in `/config/config.xml` on the
persistent Synology volume, in its `<AllowedHosts>` setting. It must include
`prowlarr.styxut.net` (currently `192.168.0.13;prowlarr.styxut.net`) for HAProxy
requests to succeed. The config file is intentionally not committed because it
contains the Prowlarr API key. Preserve the existing allowlist entries when
changing it.
