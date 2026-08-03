<p align="center">
  <a href="https://sp-night.github.io">
    <img src="https://raw.githubusercontent.com/sp-night/sp-night.github.io/main/public/logo-noite.svg" width="120" alt="SP Night — the Pico do Jaraguá at dusk, aviation beacon lit, the city's lights at the foot of the range">
  </a>
</p>

<h1 align="center">SP Night</h1>

<p align="center">
  <strong>The sodium lamp turns the whole city this colour.</strong><br>
  A dark colour scheme with São Paulo as its reference — the sodium street lamp,<br>
  exposed concrete, the free span of the MASP, the drizzle before the rain.
</p>

<p align="center">
  <a href="https://sp-night.github.io"><strong>sp-night.github.io</strong></a>
  &nbsp;·&nbsp;
  <a href="https://sp-night.github.io/palette">palette</a>
  &nbsp;·&nbsp;
  <a href="https://sp-night.github.io/spec">spec</a>
  &nbsp;·&nbsp;
  <a href="https://sp-night.github.io/ports">ports</a>
</p>

---

## Three flavours, all dark

Not one palette at three brightnesses — three ways of looking at the same city.

| | |
|---|---|
| **Noite Paulista** | the city at 3am; blue-violet dark, the sodium lamp burning warm on top |
| **Garoa** | the same window through the drizzle; flat grey, chroma near zero |
| **Pico do Jaraguá** | the same night from the highest point; the dark turned towards the forest |

## Ports

Plain text files. No build step, nothing to compile.

| | |
|---|---|
| [**ghostty**](https://github.com/sp-night/ghostty) | the full 16-colour ANSI mapping, cursor, selection, split dividers |
| [**kitty**](https://github.com/sp-night/kitty) | ANSI, cursor, splits, the tab bar and the three mark slots |
| [**eza**](https://github.com/sp-night/eza) | a native `theme.yml` — file kinds, permissions, sizes, git status |

## How it holds together

Every colour is written down once. A role layer names a palette key, and a port
names a role — never a colour. Move `syntax.keyword` in one file and every port
changes together.

```
palette          22 colours per flavour — the only place a hex is written
    ↓
roles            every role names a palette key, never a colour
    ↓
ports            a mapping asks for a role, never a colour
```

**No hex in any port was picked by hand**, including the previews — those are
synthetic SVGs drawn from the palette, so they cannot show a colour you will not
get.

**Contrast is a gate, not a promise.** 70 pairs per flavour are measured on every
build, and the build fails when one falls short. An unreadable comment is the
number-one issue of every popular dark theme, and always because nobody measured.

The engine and the full specification live in
[**sp-night/sp-night**](https://github.com/sp-night/sp-night). Adding a port is
three steps, and only one of them needs a human.

## Contributing

A port is a mapping, not a copy of colours. Start with
[the spec](https://sp-night.github.io/spec), then
[docs/port-creation.md](https://github.com/sp-night/sp-night/blob/main/docs/port-creation.md).

If an app needs something the roles do not offer, that is a real finding — open an
issue rather than reaching for the palette.

MIT.
