# Provador Virtual — Moritz

Widget do Provou Levou para as páginas de produto da Moritz.

- Plataforma: Nuvemshop
- Domínio: `moritzoculos.com.br`
- Carregamento: script externo instalado diretamente na Nuvemshop
- Limite diário: 3 provas por telefone ou IP
- Referências: prioriza fotos da galeria em que o produto aparece no rosto

## Código instalado na Nuvemshop

O carregador abaixo é seguro para ficar no código global da loja: ele só executa
nas páginas de produto da Moritz.

```html
<script>
(function () {
  if (!/(^|\.)moritzoculos\.com\.br$/i.test(location.hostname)) return;
  if (!/^\/produtos\/[^/]+\/?$/i.test(location.pathname)) return;
  if (window.__PL_MORITZ_LOADED__) return;
  window.__PL_MORITZ_LOADED__ = true;

  var script = document.createElement('script');
  script.src = 'https://lucasdecamargosilva.github.io/nuvemshopmoritz/widget-moritz.js';
  script.async = true;
  document.head.appendChild(script);
})();
</script>
```
