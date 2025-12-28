# Instruções rápidas para agentes AI (Copilot)

Resumo: este repositório é um portfólio estático de uma página (único arquivo principal: `index.html`). Não há sistema de build nem testes automatizados; alterações são editadas diretamente no HTML/CSS e publicadas como páginas estáticas (GitHub Pages em projetos vinculados).

Principais pontos que um agente deve saber

- Arquitetura "big picture":
  - Arquivo principal: `index.html` (HTML + CSS inline). Conteúdo e estilo estão centralizados nele.
  - Assets (imagens, arquivos .zip de projetos) ficam na raiz do repositório e são referenciados diretamente por nome (ex.: `Captura de tela ...png`, `calculadora simples.zip`).
  - Dependências externas via CDN: Font Awesome e Google Fonts (não há bundler/lockfile).

- Convenções do projeto (observadas no código):
  - Classes e ids em PT-BR (ex.: `.txtsobremim`, `.projetocard1`, `#projetos`). Mantenha termos em português ao adicionar classes novas para consistência.
  - Estilos internos: todo o CSS está dentro de `<style>` no `head`. Se mover CSS para arquivo externo, atualize referências e teste localmente.
  - Nomes de arquivos podem conter espaços e caracteres especiais (mantenha cuidado ao renomear — atualize todas as referências).

- Padrões de edição e revisão (ações específicas):
  - Para editar conteúdo, abra `index.html` e faça mudanças diretas; verifique visualmente no navegador ou usando Live Server (`Extensão: Live Server`) ou um servidor simples (`python -m http.server 8000` ou `npx serve .`).
  - Ao alterar imagens: otimize (compressão / WebP) e substitua mantendo o mesmo nome quando possível para evitar quebrar links.
  - Ao mudar urls externas (links para GitHub Pages): confirme que as páginas externas continuam acessíveis antes de abrir PR.
  - Ao alterar estrutura HTML/CSS: inclua uma captura de tela nas PRs para facilitar revisão visual.

- Integrações & pontos sensíveis:
  - Links para projetos apontam para GitHub Pages ou repositórios (ex.: `https://raf693.github.io/...`). Evite alterar sem validação.
  - CDN removals ou atualizações de versão (Font Awesome / Google Fonts) podem afetar ícones/estilos — teste visualmente após qualquer alteração.

- Observações encontradas no código (ações imediatas):
  - Há um caractere `]` extra na tabela de notas (linha com nota `8.90`): corrija `8.90</td>]` → `8.90</td>` para evitar HTML inválido.
  - A página usa `lang="pt-BR"` e meta description; preservar essas informações melhora SEO.

- Sugestões práticas que o agente pode propor (opcionais, sujeitas à aprovação do mantenedor):
  - Externalizar CSS para `styles.css` em `assets/` e atualizar `index.html` (faça PR separado e inclua screenshots).
  - Otimizar imagens e unificar convenção de nomes (substituir espaços por `-` ou `_`); atualize referências em single PR cuidadosamente.
  - Adicionar um pequeno README com instruções de preview local e deploy (se o mantenedor desejar).

Seções de referência rápida (exemplos do código):
- Nav fixa: `.botoes .btn` (links ancorados: `#txtsobremim`, `#projetos`, `#contato`).
- Cards de projeto: `.projetocard1`, `.projetocard2`, `.projetocard3` dentro de `#projetos`.
- Downloads de projeto: links em `a.botao-download` apontando para arquivos `.zip` na raiz.

Perguntas / pontos abertos
- Gostaria que eu:
  - separasse o CSS em um arquivo e abrisse um PR de exemplo? ✅
  - corrigisse o `]` mencionado e criasse um PR com essa correção? ✅

---
Se quiser, faço as mudanças (ex.: correção rápida do `]` + um README curto) e abro PR com screenshots. Diga qual opção prefere.