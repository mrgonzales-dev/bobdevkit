<script setup>
const lines = [
  { cls: 'usr', text: '$ curl -fsSL https://raw.githubusercontent.com/mrgonzales-dev/ibmbob-hackathon/main/bobdevkit/install.sh | sh' },
  { cls: 'ban', text: '██████╗  ██████╗ ██████╗     ██████╗ ███████╗██╗   ██╗██╗  ██╗██╗████████╗' },
  { cls: 'ban', text: '██╔══██╗██╔═══██╗██╔══██╗    ██╔══██╗██╔════╝██║   ██║██║ ██╔╝██║╚══██╔══╝' },
  { cls: 'ban', text: '██████╔╝██║   ██║██████╔╝    ██║  ██║█████╗  ██║   ██║█████╔╝ ██║   ██║   ' },
  { cls: 'ban', text: '██╔══██╗██║   ██║██╔══██╗    ██║  ██║██╔══╝  ╚██╗ ██╔╝██╔═██╗ ██║   ██║   ' },
  { cls: 'ban', text: '██████╔╝╚██████╔╝██████╔╝    ██████╔╝███████╗ ╚████╔╝ ██║  ██╗██║   ██║   ' },
  { cls: 'ban', text: '╚═════╝  ╚═════╝ ╚═════╝     ╚═════╝ ╚══════╝  ╚═══╝  ╚═╝  ╚═╝╚═╝   ╚═╝   ' },
  { cls: 'res', text: '  terminal-native skills for your AI agent' },
  { cls: 'res', text: '' },
  { cls: 'res', text: 'downloading bobdevkit from github.com/mrgonzales-dev/ibmbob-hackathon@main' },
  { cls: 'prm', text: '? which skills? (space to toggle, enter to confirm)' },
  { cls: 'sel', text: '❯ [x] bob-upgrade-check' },
  { cls: 'chk', text: '  [x] bob-impact' },
  { cls: 'chk', text: '  [x] bob-pr' },
  { cls: 'res', text: 'detecting agent environments…' },
  { cls: 'res', text: '  found: .bob,.devin,.cursor' },
  { cls: 'prm', text: '? install into which? (enter to pick)' },
  { cls: 'sel', text: '❯ .bob/skills' },
  { cls: 'opt', text: '  .devin/skills' },
  { cls: 'opt', text: '  .cursor/skills' },
  { cls: 'opt', text: '  all of the above' },
  { cls: 'res', text: 'installing into .bob/skills' },
  { cls: 'okl', text: '✓ bob-upgrade-check installed' },
  { cls: 'okl', text: '✓ bob-impact installed' },
  { cls: 'okl', text: '✓ bob-pr installed' },
  { cls: 'res', text: '' },
  { cls: 'okl', text: '✓ done — restart your agent' },
]
</script>

<template>
  <section class="install" id="install">
    <h2 class="reveal">install</h2>
    <p class="hint reveal">One command. Pick your skills, pick where they land.</p>
    <div class="term reveal">
      <div class="term-bar">
        <span class="dot"></span><span class="dot"></span><span class="dot"></span>
        <span class="term-title">bobdevkit — install.sh</span>
      </div>
      <div class="term-body">
        <p
          v-for="(l, i) in lines"
          :key="i"
          class="line"
          :class="l.cls"
          :style="{ '--d': i * 0.3 + 's' }"
        >{{ l.text || ' ' }}</p>
        <p class="line" :style="{ '--d': lines.length * 0.3 + 's' }">$ <span class="cursor">▌</span></p>
      </div>
    </div>
  </section>
</template>

<style scoped>
.install {
  max-width: 720px;
  margin: 0 auto;
  padding: 64px 24px;
}

h2 {
  font-size: clamp(28px, 5vw, 44px);
  text-transform: uppercase;
  letter-spacing: 3px;
  margin: 0 0 12px;
  border-bottom: 4px solid var(--blue);
  padding-bottom: 12px;
}

.hint {
  color: var(--muted);
  font-size: 15px;
  margin: 0 0 36px;
}

.term {
  border: 3px solid var(--ink);
  box-shadow: 10px 10px 0 var(--purple);
  background: #07090f;
  font-size: 13.5px;
  text-align: left;
}

.term-bar {
  display: flex;
  align-items: center;
  gap: 8px;
  padding: 10px 14px;
  border-bottom: 2px solid var(--dim);
  background: var(--panel);
}

.dot {
  width: 11px;
  height: 11px;
  border: 2px solid var(--ink);
}
.dot:nth-child(1) { background: var(--purple); }
.dot:nth-child(2) { background: var(--blue); }
.dot:nth-child(3) { background: var(--dim); }

.term-title {
  margin-left: 8px;
  color: var(--muted);
  font-size: 12px;
  letter-spacing: 1px;
}

.term-body { padding: 16px 18px; }

.line {
  margin: 0 0 5px;
  white-space: pre-wrap;
  opacity: 0;
  animation: type-in 0.01s var(--d) forwards;
}

.usr { color: var(--ink); font-weight: 700; }
.ban { color: var(--purple); font-weight: 700; font-size: 11px; line-height: 1.25; }
.prm { color: var(--blue); font-weight: 700; }
.sel { color: #fff; background: var(--blue); font-weight: 700; }
.opt { color: var(--muted); }
.chk { color: var(--purple); }
.res { color: var(--muted); }
.okl { color: #4ade80; }

.cursor { animation: blink 1s steps(1) infinite; color: var(--blue); }

@keyframes type-in { to { opacity: 1; } }
@keyframes blink { 50% { opacity: 0; } }

@media (prefers-reduced-motion: reduce) {
  .line { animation: none; opacity: 1; }
  .cursor { animation: none; }
}
</style>
