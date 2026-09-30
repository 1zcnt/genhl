# genhl

A syntax highlighter that turns C or x86 AT&T assembly into a self-contained
HTML snippet (a `<style>` block plus `<pre><code>`), so a static page can show
highlighted code without JavaScript. The lexers are written in lex, the colors
live in `theme.h`.

## Build

```sh
make            # needs cc and lex/flex
```

## Usage

```
genhl [c | asmatt] < source > snippet.html
```

The language defaults to C.

```sh
$ printf 'int main(void) { return 1 && 2; }\n' | ./genhl c
<style>.stx_root{...}...</style><div class="stx_root"><pre><code><span class="stx6">int</span> <span class="stx5">main</span>(<span class="stx6">void</span>) { ...
```
