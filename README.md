# Recursor configuration layout

This repository now groups related settings by scope and load order while preserving the original configuration values.

## File map
- `recursor.d/00-core-server.yml` — global recursor defaults (RFC serving, PSL file, TTL override, qname minimization toggle).
- `recursor.d/00-logging.yml` — logging level and RPZ/common error logging switches.
- `recursor.d/01-incoming-access.yml` — listeners, ACLs, and EDNS/transport tuning for clients.
- `recursor.d/02-outgoing-tuning.yml` — source addressing, EDNS size, timeouts, and throttling exceptions for upstream queries.
- `recursor.d/10-dnssec.yml` — DNSSEC validation and aggressive NSEC cache settings.
- `recursor.d/20-rpz-feeds.yml` — all RPZ policy zones (local policies, mtheofy.com, abuse.ch, hagezi, ioc2rpz).
- `recursor.d/30-upstreams.yml` — authoritative zone files and recursive forwarders (root zone only) plus reference examples.
- `recursor.d/32-ecs.yml` — ECS minimum TTL override.
- `recursor.d/40-cache.yml` — stale-serving settings and refresh percentage.

## Notes
- Numeric prefixes keep related topics spaced for future inserts (00/01/02…40/50).
- RPZ feeds and upstream sources are consolidated so policy zones and data sources live in single files, reducing cross-file hunting.
- No configuration values were altered during this reorganization; only file names and placement changed.
