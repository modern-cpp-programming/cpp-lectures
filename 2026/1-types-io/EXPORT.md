# Marp exports

The PDF, PPTX, and `jpg/` images are exported from `1-types-io.md`
with Marp CLI 4.5.0 and the repository's `themes/2022cpl.css` theme.
Each format contains 22 slides. The PPTX uses Marp's standard image-based
slides, preserving the rendered layout.

## Windows browser configuration

If VS Code reports `Failed to launch the browser process`, explicitly
select the installed browser in User Settings (JSON):

```json
{
  "markdown.marp.browser": "edge",
  "markdown.marp.browserPath": "C:\\Program Files (x86)\\Microsoft\\Edge\\Application\\msedge.exe"
}
```

Adjust the path if Edge is installed elsewhere. Reload the VS Code window
after changing the setting, then run `Marp: Export Slide Deck` again.

## Command-line export

From the repository root, run the following PowerShell commands:

```powershell
$deck = '2026/1-types-io/1-types-io.md'
$options = @('--html', '--allow-local-files', '--theme', 'themes/2022cpl.css',
  '--browser', 'edge', '--browser-path',
  'C:\Program Files (x86)\Microsoft\Edge\Application\msedge.exe')
npx --yes @marp-team/marp-cli@4.5.0 $deck @options --pdf --pdf-notes --pdf-outlines -o 2026/1-types-io/1-types-io.pdf
npx --yes @marp-team/marp-cli@4.5.0 $deck @options --pptx -o 2026/1-types-io/1-types-io.pptx
New-Item -ItemType Directory -Force 2026/1-types-io/jpg | Out-Null
npx --yes @marp-team/marp-cli@4.5.0 $deck @options --images jpeg -o 2026/1-types-io/jpg/1-types-io.jpg
```

Local file access is needed for this deck's `figs/` images.
