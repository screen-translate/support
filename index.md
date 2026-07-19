---
title: Support
---

# Support

Contact us at [screen-translate@proton.me](mailto:screen-translate@proton.me).

<button class="copy-button" type="button" aria-label="Copy email address" onclick="copyEmail(this)">
  <svg viewBox="0 0 16 16" aria-hidden="true">
    <rect x="5.5" y="5.5" width="8" height="8" rx="1.5"></rect>
    <path d="M10.5 5.5v-2A1.5 1.5 0 0 0 9 2H3.5A1.5 1.5 0 0 0 2 3.5V9A1.5 1.5 0 0 0 3.5 10.5h2"></path>
  </svg>
  <span data-copy-label aria-live="polite">Copy</span>
</button>

<style>
.copy-button {
  appearance: none;
  display: inline-flex;
  align-items: center;
  gap: 6px;
  padding: 7px 12px;
  color: #1d1d1f;
  font: 500 14px/1 -apple-system, BlinkMacSystemFont, "SF Pro Text", sans-serif;
  background: linear-gradient(#ffffff, #f1f1f1);
  border: 1px solid rgba(0, 0, 0, 0.18);
  border-radius: 999px;
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.12), inset 0 1px 0 rgba(255, 255, 255, 0.8);
  cursor: pointer;
  transition: background 120ms ease, box-shadow 120ms ease, transform 120ms ease;
}

.copy-button:hover {
  background: linear-gradient(#ffffff, #e9e9e9);
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.14), inset 0 1px 0 rgba(255, 255, 255, 0.8);
}

.copy-button:active {
  background: #e6e6e6;
  box-shadow: inset 0 1px 2px rgba(0, 0, 0, 0.12);
  transform: translateY(1px);
}

.copy-button:focus-visible {
  outline: 3px solid rgba(0, 122, 255, 0.35);
  outline-offset: 2px;
}

.copy-button svg {
  width: 14px;
  height: 14px;
  fill: none;
  stroke: currentColor;
  stroke-linecap: round;
  stroke-linejoin: round;
  stroke-width: 1.7;
}
</style>

<script>
async function copyEmail(button) {
  const email = "screen-translate@proton.me";

  try {
    await navigator.clipboard.writeText(email);
  } catch {
    const textArea = document.createElement("textarea");
    textArea.value = email;
    textArea.style.position = "fixed";
    textArea.style.opacity = "0";
    document.body.appendChild(textArea);
    textArea.select();
    document.execCommand("copy");
    textArea.remove();
  }

  const label = button.querySelector("[data-copy-label]");
  label.textContent = "Copied";
  button.setAttribute("aria-label", "Email address copied");

  setTimeout(() => {
    label.textContent = "Copy";
    button.setAttribute("aria-label", "Copy email address");
  }, 1500);
}
</script>
