# Rota Diária — Painel do Motoboy

Painel web para registro e acompanhamento de entregas, com controle por tipo (Varejo / Mercado), agrupamento semanal e persistência local no navegador.

## Funcionalidades

- Registro de entregas por data, tipo e quantidade
- Resumo mensal: total ganho, quantidade de entregas, dias rodados e média diária
- Histórico agrupado por semana (sexta a quinta) e por dia
- Edição e exclusão de entregas via modal
- Configuração dos valores por entrega (Varejo e Mercado) salvos separadamente
- Navegação entre meses
- Dados persistidos via `localStorage` — sobrevivem ao fechamento do navegador

## Tecnologias

- HTML + CSS puro (sem framework de estilo)
- React 18 via CDN (sem build, sem Node.js)
- `localStorage` para persistência

## Como usar localmente

Abra o arquivo `painel-entregas.html` diretamente no navegador. Não precisa de servidor.

## Como publicar no Vercel

1. Crie uma pasta com o arquivo `painel-entregas.html` renomeado para `index.html`
2. Acesse [vercel.com](https://vercel.com) e faça login
3. Clique em **Add New > Project**
4. Arraste a pasta ou conecte o repositório GitHub
5. Clique em **Deploy** — sem nenhuma configuração adicional

## Estrutura de dados

Os dados ficam salvos no `localStorage` do navegador sob duas chaves:

| Chave | Conteúdo |
|---|---|
| `rotadiaria:entries` | Array de entregas registradas |
| `rotadiaria:rates` | Valores por entrega (Varejo e Mercado) |

Cada entrega tem o formato:

```json
{
  "id": "1719349200000-abc12",
  "date": "2026-06-26",
  "tipo": "varejo",
  "quantidade": 3
}
```

## Observações

- Os dados ficam salvos **por dispositivo e por domínio**. Trocar de celular ou de navegador não sincroniza os dados.
- Limpar os dados do site no navegador apaga tudo. Use a opção "Apagar todos os dados" dentro do app para um reset controlado.
- O app não requer conexão com internet após o primeiro carregamento (exceto para carregar as fontes do Google Fonts).
