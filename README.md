# Projeto: Terminal → Placa-mãe Interativa

Este projeto começa com um terminal que se multiplica até alcançar 1964 instâncias. Ao atingir esse marco, o fluxo redireciona automaticamente para uma página de placa-mãe interativa (`placa.html`). A partir dela, é possível abrir páginas específicas, como a da CPU (`cpu.html`).

## Arquivos principais

- `terminal-simples.html`: tela inicial com terminais que se multiplicam e redirecionamento para `placa.html` ao chegar em 1964.
- `placa.html`: placa-mãe interativa (CPU, RAM A/B, PCIe x16, capacitores e POWER).
  - Clique em CPU → abre `cpu.html`.
  - Clique em POWER → volta para a página anterior (`history.back`) ou para `terminal-simples.html`.
- `cpu.html`: página dedicada da CPU com controle de clock que ajusta o brilho do chip e botão POWER para voltar.
- `prompts-log.md`: histórico de prompts usados no projeto e área para registrar os próximos.

## Fluxo de navegação

1. `terminal-simples.html` → quando `Terminais >= 1964` → redireciona para `placa.html`.
2. `placa.html` → clicar em `CPU` → `cpu.html`.
3. `cpu.html` → botão POWER → volta para `placa.html` (se houver histórico) ou retorna para `terminal-simples.html`.
4. Em `placa.html`, clicar em POWER também volta para a página anterior.

## Prompts e manutenção

- O arquivo `prompts-log.md` contém:
  - Lista dos prompts já usados (histórico inicial)
  - Seção "Próximos prompts" para registrar novas solicitações
- Ao surgir um novo prompt, acrescente-o ao final do arquivo, mantendo a ordem cronológica.

## Como editar/estender

- Para adicionar novas páginas de componentes (ex.: RAM, PCIe):
  1. Crie um novo arquivo `.html` inspirado em `cpu.html`.
  2. Em `placa.html`, ajuste o manipulador de clique para redirecionar para a nova página do componente.
- Para alterar o comportamento visual (ex.: brilho, opacidade):
  - Ajuste estilos ou scripts nos arquivos correspondentes.

## Requisitos e compatibilidade

- Projeto estático: basta abrir os arquivos `.html` no navegador.
- Não há dependências externas.

## Observações

- A navegação usa `history.back()` quando disponível; caso contrário, faz fallback para a página principal.
- O design utiliza gradientes e sombras para um visual neon/cyberpunk.
