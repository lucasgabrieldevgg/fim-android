# Fork: Fim! Android

This repository is a fork of [`binwiederhier/ntfy-android`](https://github.com/binwiederhier/ntfy-android)
(version 1.25.2), the official Android client for [ntfy](https://ntfy.sh), **© Philip C. Heckel and
contributors, licensed under the Apache License 2.0** (see [`LICENSE`](LICENSE)).

## What "Fim!" changes from upstream

Fim! ("The End!") is a rebrand aimed at one use case: getting notified when an AI agent finishes a
task. The agent's last action is a REST call to a Fim! server (or straight to ntfy.sh), and the user
receives a push with a custom title — optionally with an alarm. Web app: <https://fim-flax.vercel.app>.

Changes made in this fork, per Apache 2.0 §4(b):

1. **Application name** — `ntfy` → `Fim!` (`app/src/main/res/values/values.xml`).
2. **Launcher icons** — replaced with the Fim! green exclamation badge (all `mipmap-*` layers,
   legacy + adaptive + monochrome). The ntfy bell was not reused.
3. **Application ID** — `io.heckel.ntfy` → `gg.lucasgabrieldevgg.fim`, so Fim! installs
   side-by-side with the official ntfy app (`app/build.gradle`).
4. **Version** — `1.25.2` → `1.25.2-fim.1`.

Everything else — connection handling, background service, notifications, settings — is upstream
code, unmodified. The default server remains `https://ntfy.sh`, which powers the push delivery.

## Credits

- **ntfy and ntfy-android**: [Philip C. Heckel (binwiederhier)](https://github.com/binwiederhier) and
  the ntfy contributors — Apache License 2.0. This fork exists thanks to their work; consider
  [sponsoring ntfy](https://github.com/sponsors/binwiederhier).
- **Fim! rebrand**: [lucasgabrieldevgg](https://github.com/lucasgabrieldevgg).

## Build

```bash
./gradlew :app:assembleFdroidRelease   # no Firebase, background WebSocket push
```
