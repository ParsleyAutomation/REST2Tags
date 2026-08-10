# REST to Tags

Turn any REST API into live Ignition tags — that go bad when the API does.

Point the module at a URL, click the value you want in the response, and get a real Ignition tag:
historised, bindable, alarmable, and honest about when it stopped updating. No scripting.

**Free edition polls one API URL**, with as many tags from it as that endpoint returns. A license
key removes the limit.

---

## Why not just a script?

The usual approach is a gateway timer script calling `system.net.httpGet` and writing memory tags.
It works until the API stops answering — then the script errors, the memory tag keeps its last
value at **Good** quality, and its timestamp keeps advancing because the tag was written recently.
An operator sees a healthy, freshly-stamped number that is hours old.

REST to Tags reports the truth instead:

| The API is | The tag shows |
|---|---|
| Answering | the value, Good quality, the time it was retrieved |
| Briefly unreachable | the last value, **Stale**, with its real age |
| Down, rejecting, or misconfigured | **Bad** quality, and a `SourceUnavailable` alarm fires |

The timestamp is when the data was *retrieved*, never when the last attempt happened. A stalled
source reports its true age.

## Download

Get the latest `.modl` from [Releases](../../releases).

The module is signed with Central Valley Ignition's certificate. Ignition will ask you to accept
it on first install. Verify the fingerprint matches:

```
SHA-256  FC:62:F4:68:A5:0D:AA:57:D4:6E:B6:05:BE:C0:5E:C9:C4:C3:DE:79:A5:14:02:20:C8:9B:92:07:CD:6A:A1:DF
```

## Requirements

- Ignition **8.3.0 or later**. Built against the 8.3 SDK; it will not install on 8.1.
- Works on Standard, Edge and **Maker** editions.
- The gateway needs network access to whatever endpoints you configure. Nothing else — the module
  never contacts CVI.
- JSON responses. XML and CSV are not supported.

## Install

1. Gateway → **Config → Modules → Install or Upgrade a Module…**
2. Choose the `.modl` you downloaded and click **Install**.
3. Accept the certificate when prompted.

The module appears under **Config → Connections → REST to Tags**.

## Add a source

1. Open **Config → Connections → REST to Tags** and click **Add source**.
2. Paste the **URL** to poll and choose an authentication method if the API needs one.
3. Press **Test**. The gateway calls the endpoint and shows the response as a tree.
4. **Tick the values** you want. The data type is worked out from what came back.
5. Give them a folder and a poll rate, and **Save**.

Tags appear under the `RestTags` provider within seconds. No gateway restart.

Changes always apply to the running gateway — adding, editing and removing sources never requires
a restart.

## Authentication

- **None** — open APIs.
- **API key** — sent as a header you name.
- **OAuth2 client credentials** — the gateway fetches a token, caches it, refreshes it before it
  expires, and re-fetches on a 401.

Credentials are encrypted at rest with the gateway's own encryption service, and the configuration
page never receives them — it shows `••••••` and leaves stored values untouched unless you type a
new one. A copy of the config file, or a gateway backup, contains no usable credential.

## What you get per source

Alongside the value tag, each source publishes diagnostics: current quality, how old the data is,
the consecutive failure count, the last error, and the time of the last successful read. They stay
readable at Good quality even when the source itself is bad — so a screen can show *why* a value
has stopped moving.

Every value tag carries a `SourceUnavailable` alarm that fires on bad quality, and can be
historised like any other tag.

## Write-back

Give a source a write URL and writing the tag POSTs the value to it. A rejected write surfaces as
a failed write with the reason, rather than being silently swallowed and then contradicted by the
next poll.

## Editions

| | Free | Pro | Integrator |
|---|---|---|---|
| API URLs polled | 1 | Unlimited | Unlimited |
| Tags per URL | Unlimited | Unlimited | Unlimited |
| Gateways per key | — | 1 | Any |
| Every other feature | Yes | Yes | Yes |

**Free** is the full module, not a crippled demo — one API URL, every feature working. It is enough
to prove the thing on a real endpoint before spending anything.

**Pro** removes the URL limit on one gateway. Nothing else is gated; there is no feature behind a
paywall and no middle plan that strands you part-way through building a screen.

**Integrator** is the same licence for system integrators, valid on any gateway you deploy to. If
you put the same stack in front of a dozen clients, this is one key instead of a purchase order per
project.

Sources beyond the limit stay configured and visible — they simply do not poll. A configuration
survives a lapsed or absent licence intact and resumes the moment a key is applied.

**To buy Pro:** open the License card on the config page, copy your **Gateway ID**, and send it
with your order. Keys are issued against that ID. Paste the key into the same card and press
Apply — it takes effect immediately, with no reinstall and no restart.

**To buy Integrator:** just ask. There is no Gateway ID to collect, so the key works on client
gateways you have not built yet.

Licensing is entirely offline. The module makes no activation call and needs no internet access to
CVI, so it works on air-gapped OT networks.

## Support

Open an [issue](../../issues) or email support@centralvalleyignition.com.

Please include your Ignition version, the module version, what the source's diagnostics tags show,
and the relevant lines from `wrapper.log`.

## License

Proprietary. See [EULA.md](EULA.md).

**No third-party code.** The module bundles no external libraries — only Central Valley Ignition's
own code. This is enforced by an automated check on every build, so there are no third-party
licenses or CVEs to review before putting it on a gateway.

---

Central Valley Ignition · [centralvalleyignition.com](https://centralvalleyignition.com)
