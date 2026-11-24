# winemac.so with DXMT exports

Builds Wine's macOS window driver (`winemac.so`) from the official Wine source
(https://github.com/wine-mirror/wine) plus one small patch, so that
[DXMT](https://github.com/3Shain/dxmt) (Direct3D 10/11 on Metal) can attach to Wine windows.
Used by the free, open project Emulate Everything.

- `patches/0001-winemac-export-macdrv_functions-for-DXMT.patch` — exports the
  `macdrv_functions` table DXMT looks for. Ported to Wine 11.x from CodeWeavers'
  CrossOver hack 22435 (crossover-sources-20251106), as carried by MacPorts' wine-devel.
- `.github/workflows/build.yml` — builds it on a GitHub-hosted Intel Mac
  (Actions → "Build winemac.so with DXMT exports" → Run workflow). The result is a
  downloadable artifact with `winemac.so`, the patch and build info.

The built file replaces `lib/wine/x86_64-unix/winemac.so` in a Wine build of the
same version. Wine is licensed under the LGPL 2.1 or later; this patch is under the same licence.

---

# winemac.so с поддержкой DXMT

Собирает оконный модуль Wine для macOS (`winemac.so`) из официального исходного
кода Wine с одной небольшой правкой, чтобы DXMT (DirectX 10/11 через Metal) мог
работать с окнами Wine. Используется в бесплатном открытом проекте Emulate Everything.

Запуск: вкладка Actions → «Build winemac.so with DXMT exports» → Run workflow.
Готовый файл скачивается внизу страницы запуска, в разделе Artifacts.
Лицензия — LGPL 2.1 или новее, как у самого Wine.
