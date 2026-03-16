# Portal Interativo de Transparência e Status financeiro

> **Nota de Conformidade e Engenharia:** Este repositório documenta a arquitetura de *Frontend* e as lógicas de *Data Visualization* de uma aplicação governamental corporativa. Por motivos de conformidade (NDA), o código-fonte que contém os dados sensíveis da planilha e as rotas exatas da API não é público.

## Visão Geral
Sistema *Single Page Application* (SPA) desenvolvido em Google Apps Script para atuar como um painel de transparência de repasses financeiros. A aplicação permite que instituições parceiras consultem autonomamente o *status* de seus contratos (via código de instrumento jurídico), eliminando gargalos de atendimento manual do setor financeiro.

## Arquitetura e UI/UX
* **Data Visualization (Progresso Linear):** O desafio central era simplificar o entendimento de um fluxo burocrático complexo. Foi implementada uma lógica de mapeamento de status (`statusMap`) que converte *strings* do banco de dados ("A PAGAR", "EM LIQUIDAÇÃO") em *milestones* numéricos (0 a 100), alimentando uma barra de progresso visual baseada em CSS dinâmico.
* **Componentização Responsiva (Vanilla JS):** O frontend foi arquitetado sem a dependência de frameworks pesados (React/Angular). A manipulação do DOM (Criação de Cards de Resultado e Seletor de Competências) ocorre programaticamente em JavaScript puro, garantindo extrema leveza e compatibilidade com navegadores legados do setor público.
* **Filtragem de Estados (State Management):** Implementação de lógica de retenção de dados globais (`globalData`), permitindo que o usuário filtre o histórico de pagamentos por "Mês de Competência" instantaneamente no *Client-side*, sem a necessidade de realizar novos *fetches* custosos ao servidor.

**Stack:** Google Apps Script, HTML5, CSS3, JavaScript (Vanilla DOM Manipulation).
