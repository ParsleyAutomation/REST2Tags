# Release notes

## 1.0.0

First public release.

**What it does.** Polls REST APIs into Ignition tags with correct quality codes, so a source that
stops answering is visible rather than silently frozen at its last value.

### Core

- Poll any JSON REST endpoint into an Ignition tag, on a per-source schedule from 5 seconds to
  hourly. Each source polls independently, so a slow endpoint delays only its own tag.
- Quality reflects reality: **Good** while answering, **Stale** while a recent value is still worth
  showing, then bad. The value's timestamp records when the data was *retrieved*, so a stalled
  source reports its true age instead of looking freshly written.
- Failures are distinguished rather than lumped together — unreachable, rejected credentials,
  unparseable response, and wrong mapping path each report differently.
- A `SourceUnavailable` alarm on every value tag, using Ignition's native bad-quality alarm mode.
- Optional tag history, configured per tag.
- Write-back: a tag write POSTs to a configured URL, and a rejection surfaces on the write.

### Configuration

- Gateway page under **Config → Connections → REST to Tags**.
- Press **Test** and the gateway calls the endpoint, then shows the response as a tree — tick the
  values you want and the data type is inferred from what came back.
- Multiple tags from one endpoint in a single step, with Select all / Select none.
- Changes apply to the running gateway within seconds. No restart, ever.
- Data types can be overridden. APIs that report numbers as text still produce numeric tags.
- Deeply nested and array values are supported; the path is chosen by clicking, not typing.

### Authentication

- API key sent as a header you name.
- OAuth2 client credentials, with token caching, refresh ahead of expiry, and automatic re-fetch
  on a 401.

### Security

- Credentials encrypted at rest using the gateway's own encryption service, so Ignition owns the
  key material.
- The configuration page never receives credentials — it shows `••••••` and preserves stored
  values untouched.
- No phone-home. Licensing is an offline signed token; the module contacts nothing but the
  endpoints you configure.
- No bundled third-party libraries, enforced by an automated check on every build.

### Licensing

- Free edition polls one API URL, with unlimited tags from it.
- A license key removes the limit, applied from the config page with no restart.
- Three editions: Free (1 URL), Pro (unlimited URLs, one gateway) and Integrator (unlimited URLs,
  any gateway). Only the URL cap and the gateway binding differ — no feature is behind a tier.
- Sources over the limit stay configured and simply do not poll, so a configuration survives a
  lapse and resumes on upgrade.

### Requirements

Ignition 8.3.0 or later. Standard, Edge and Maker editions.

### Known limitations

- JSON responses only. XML and CSV are not supported.
- Credentials are entered per source; Ignition's Secret Provider system is not yet supported.
- The certificate is self-signed, so Ignition asks you to accept it on first install.
