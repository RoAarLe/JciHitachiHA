# Vendored LibJciHitachi

`JciHitachi/` is a copy of the `JciHitachi` package from LibJciHitachi,
taken from a not-yet-merged upstream pull request series so that one offline
device no longer makes the whole integration fail to load.

- Upstream project: https://github.com/qqaatw/LibJciHitachi (Apache-2.0, author Allan Lin)
- Source of this copy: https://github.com/Tony427/LibJciHitachi
  - branch `split/03-control-channel`, pinned at commit
    `b03be6a18b27ee56b3b079327334e99bb3a0f7d9`
  - = LibJciHitachi master `2a56414` (1.7.2) + upstream PR #45 (`2188a13`),
    #46 (`a693cf2`, per-device availability) and #47 (`b03be6a`, control tolerance)
- License: Apache License 2.0, see `JciHitachi/LICENSE` (copied unchanged).

## Local modifications

- `JciHitachi/__init__.py`: `__version__` changed from `1.7.2` to
  `1.7.2+tony427.b03be6a` so the log shows which backend is in use.
- No other file was changed. The package only uses relative imports, so it is
  imported as `custom_components.jcihitachi_tw.vendor.JciHitachi` and does not
  clash with an installed PyPI `LibJciHitachi`.

Its runtime dependencies (`awsiotsdk`, `httpx`, `paho-mqtt`) are listed in
`manifest.json` `requirements` instead of `LibJciHitachi` itself.

Switch back to the PyPI package once upstream releases these fixes.
