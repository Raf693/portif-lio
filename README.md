# Portfólio - Rafael da Silva Alves

Descrição
--------
Site de portfólio simples (single-page) criado com HTML, CSS e alguns trechos em JavaScript. O arquivo principal é `index.html` e os assets (imagens, .zip dos projetos) ficam na raiz do repositório.

Como visualizar localmente ✅
- Método rápido (recomendado): instale a extensão Live Server no VS Code e clique em "Go Live".
- Alternativa via terminal: execute

  ```bash
  python -m http.server 8000
  ```
  e abra `http://localhost:8000` no navegador.

Arquitetura e convenções 🔧
- Arquivo principal: `index.html` (HTML e CSS inline dentro de `<style>`).
- Fonts e ícones: Google Fonts (`Material Symbols`) e Font Awesome via CDN.
- Classes e ids em português (ex.: `.txtsobremim`, `.projetocard1`). Mantenha essa convenção ao adicionar novos estilos.
- Imagens e arquivos de projeto podem conter espaços no nome — se for renomear, atualize todas as referências.

Observações e correções rápidas ⚠️
- Há um caractere `]` extra em uma linha da tabela de notas: substitua
  ```html
  8.90</td>]
  ```
  por
  ```html
  8.90</td>
  ```
  para evitar HTML inválido.

- A barra fixa inferior (`.btn`) atualmente está posicionada com `left: 0;` e os links usam `flex: 1;`, o que faz com que não pareça centralizada.
  Sugestão de CSS para centralizar a barra e preservar responsividade:
  ```css
  .btn{
    position: fixed;
    bottom: 0;
    left: 50%;
    transform: translateX(-50%);
    width: 95%; /* ou max-width: 900px */
    display: flex;
    justify-content: center;
    gap: 10px;
  }
  .btn > a{ flex: 0; }
  ```

Melhorias recomendadas (opcionais) ✨
- Externalizar o CSS para `assets/styles.css` e referenciar em `index.html` (facilita manutenção). Crie um PR separado e inclua screenshots para revisão visual.
- Otimizar imagens (compressão / WebP) e padronizar nomes de arquivos (ex.: `minha-foto.jpg`).
- Incluir um README curto (este arquivo) e adicionar instruções de contribuição e testes manuais.

Contribuição
-----------
- Para contribuições: abra uma branch, faça alterações e envie um Pull Request com descrição e screenshots das mudanças visuais quando aplicável.

Contato
------
Autor: Rafael da Silva Alves

---
Arquivo criado automaticamente para ajudar no desenvolvimento e revisão do projeto.