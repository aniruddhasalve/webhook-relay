# webhook-relay

## Webhook relay REST API

POST /hooks/{name} captures JSON payloads for inspection; GET /hooks/{name} reads recent payloads. Forwarding is an explicit optional URL.

This is a small reusable Python 3.11 service with no AI components and no runtime dependencies. It uses the standard library HTTP server so it can be copied into internal automation, extended, or deployed behind a reverse proxy.

## Run

```bash
python3 server.py
# listens on 0.0.0.0:8080
```

Send JSON requests with `Content-Type: application/json`. Every service exposes `GET /health`. See `tests/test_api.py` for request examples. External binaries are optional and are reported as clear `503`/`501` responses when not configured.

## Test

```bash
python3 -m unittest discover -s tests -v
```

## License

MIT. Use this codebase as a starting point for your own service.
