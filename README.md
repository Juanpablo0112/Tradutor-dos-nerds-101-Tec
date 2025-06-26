# Tradutor-dos-nerds-101-Tec
Tradutor do alfabeto nerd
/**
 * Copia o texto fornecido para a área de transferência.
 * @param {string} text - O texto a ser copiado.
 * @returns {Promise<void>}
 */
async function copyToClipboard(text) {
  if (navigator && navigator.clipboard && navigator.clipboard.writeText) {
    return navigator.clipboard.writeText(text);
  } else {
    // Fallback para navegadores antigos
    const textarea = document.createElement("textarea");
    textarea.value = text;
    textarea.setAttribute("readonly", "");
    textarea.style.position = "absolute";
    textarea.style.left = "-9999px";
    document.body.appendChild(textarea);
    textarea.select();
    document.execCommand("copy");
    document.body.removeChild(textarea);
  }
}
