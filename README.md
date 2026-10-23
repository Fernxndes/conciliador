# Conciliador — demonstração

Conciliação de contas a pagar: cruza o **DDA do banco**, a **exportação do ERP**
e a **base de XMLs das notas fiscais** (NF-e e CT-e), diz para cada documento se
pode pagar ou o que precisa ser conferido antes, e imprime a folha que decide o
pagamento.

Esta página é a **tela real do sistema**. O servidor original (Python/FastAPI, que
lê os arquivos e a base de notas) foi trocado por um simulador dentro do próprio
`index.html`. Todos os dados são **fictícios** e nada sai do navegador de quem
visita.

## O que dá para fazer na demonstração

- **Painel:** títulos a pagar pelas notas fiscais, filtros por período e tipo.
- **Conciliação:** rodar uma conciliação (use os arquivos de exemplo do aviso no
  canto da tela; o simulador não lê o conteúdo).
- **Conciliado:**
  - abas por situação;
  - ✓ conferir, ✗ remover, ↩ desfazer;
  - mover de categoria e mandar para depósito Itaú/Bradesco;
  - documento em mãos;
  - e-mail de cobrança por setor;
  - juros/desconto e devolução;
  - filtro por tipo;
  - impressão rápida de notas (andamento simulado);
  - resumo;
  - atualizar com nova exportação do ERP e desfazer.
- **Impressões:** folha de conferência do DDA e folhas de depósito
  (`Ctrl+P` / botão de impressão).
- **Exportações:** CSV da conciliação e CSV de conferência.
- **Histórico:** salvar, reabrir, apagar e buscar documento.

O "hoje" da demonstração é **27/10/2026**. O que você salva fica só no seu navegador;
**"Restaurar demonstração"** (no aviso do canto) volta ao estado inicial.

## O que é simulado

- A leitura do DDA, do ERP e dos XMLs: qualquer arquivo anexado devolve a mesma
  conciliação de exemplo.
- A impressão física de notas: o andamento é simulado, nada vai para impressora.
- O e-mail: abre um rascunho no programa de e-mail (`mailto:`); nada é enviado.

## Publicar no GitHub Pages

1. Crie um repositório (por exemplo, `conciliador`).
2. Envie o `index.html` (e este `README.md`) para a raiz do branch `main`.
3. No repositório: **Settings → Pages → Build and deployment → Source: Deploy from a
   branch**, escolha `main` e a pasta `/ (root)`, e salve.
4. Em um ou dois minutos o site fica em `https://<seu-usuario>.github.io/conciliador/`.

O `index.html` é autossuficiente: não usa bibliotecas externas nem internet.
