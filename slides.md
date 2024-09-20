---
theme: seriph
background: https://source.unsplash.com/collection/94734566/1920x1080
class: text-center
highlighter: shiki
lineNumbers: false
info: |
  ## Manage Modals in a Natural Way
  Presentation slides for developers.
drawings:
  persist: false
transition: slide-left
title: Manage Modals in a Natural Way
mdc: true
---

# Manage Modals in a Natural Way

with react context

Yedidya Rashi

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Press Space for next page <carbon:arrow-right class="inline"/>
  </span>
</div>

<div class="abs-br m-6 flex gap-2">
  <button @click="$slidev.nav.openInEditor()" title="Open in Editor" class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon:edit />
  </button>
  <a href="https://github.com/yourusername/your-repo" target="_blank" alt="GitHub"
    class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

---

## transition: fade-out

# What We're Going to Cover

<v-clicks>

- The current approach to managing modals in React
- Issues with the current approach
- Rethinking modal usage in React applications
- Requirements for a better modal management solution
- Introducing @ebay/nice-modal-react
- Example usage and benefits

</v-clicks>

---

layout: image-right
image: ../img/modal-example.jpg

---

# Motivation

Using modals in React can be frustrating, especially when implementing complex UIs like this:

<v-click>

- Multiple modals
- Nested modals
- Modals with dynamic content

</v-click>

---

transition: slide-up
level: 2

---

# Current Approach

```ts {all|2|4-7|all}
const Root = () => {
  const [visible, setVisible] = useState(false);
  // other logic ...
  return (
    <>
      <Main />
      <NewTicketModal visible={visible} />
    </>
  );
};
```
