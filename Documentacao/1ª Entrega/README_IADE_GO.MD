# IADEGO — Aplicação móvel (Poster / 1.ª Entrega)

![Poster do Projeto](Documentacao/1Entrega/posteriadego.jpg)


**Universidade:** [Universidade Europeia](https://www.europeia.pt/)  
**Faculdade:** IADE — Faculdade de Design, Tecnologia e Comunicação  
**Curso:** Engenharia Informática  
**Semester:** 2025-2026 / 3.º Semestre

---

## Índice

1. [Elementos do Grupo](#elementos-do-grupo)  
2. [Resumo / Poster](#resumo--poster)  
3. [Palavras-chave](#palavras-chave)  
4. [Descrição do Projeto](#descrição-do-projeto)  
5. [Enquadramento com o Briefing / Objetivos](#enquadramento-com-o-briefing--objetivos)  
6. [Público-alvo](#público-alvo)  
7. [Funcionalidades (conforme poster)](#funcionalidades-conforme-poster)  
8. [Requisitos Funcionais e Não Funcionais](#requisitos-funcionais-e-não-funcionais)  
9. [Modelo do Domínio (ER) — visão textual](#modelo-do-domínio-er---visão-textual)  
10. [Guiões de Teste (mín. 3)](#guiões-de-teste-mín-3)  
11. [Casos de Utilização (1 core + 2 adicionais)](#casos-de-utilização-1-core--2-adicionais)  
12. [Plano de Trabalho / WBS / Gantt (resumo)](#plano-de-trabalho--wbs--gantt-resumo)  
13. [Requisitos Técnicos e Ferramentas Obrigatórias](#requisitos-técnicos-e-ferramentas-obrigatórias)  
14. [Entregas e Datas (conforme briefing)](#entregas-e-datas-conforme-briefing)  
15. [Mockups / Interfaces / Figma (referência)](#mockups--interfaces--figma-referência)  
16. [Conclusão / Benefícios](#conclusão--benefícios)

---

## Elementos do Grupo

- 20230331 — David Bação  
- 202301001 — Francisco Lourinho  
- 20241805 — Vivandro Kambaza  
- 20230853 — Yosvany Nunes

---

## Resumo / Poster

O **IADEGO** é uma aplicação móvel para estudantes do IADE que permite **escolher e reservar lanches**, **levantar com QR Code**, e **usar GPS interno** para encontrar salas e locais no campus. Objetivo: eliminar filas, reduzir stress e otimizar o tempo dos alunos.

Slogan (do poster):  
**encontra o teu lanche e a tua sala. Sem filas. Sem stress.**

---

## Palavras-chave

Reserva; QR Code; Lanches; GPS interno; Campus; IADE; Mobile; App; Interativo; Experiência do Estudante.

---

## Descrição do Projeto

IADEGO é uma app mobile voltada para o ambiente académico IADE com foco principal em:

- Reservas de lanches em tempo real (evitar filas).  
- Geração de QR Code para levantar o pedido no bar (QR válido por 10 minutos).  
- GPS interno para localizar salas e pontos de interesse do campus.  
- Notificações de lembrete (pedidos prontos / tempo para próxima aula).  

A experiência no poster (escolhe → reserva → levanta com QR) é o fluxo central do produto.

---

## Enquadramento com o Briefing / Objetivos

**Contexto (L-EI — 3.º semestre):** projeto multidisciplinar que integra conhecimentos de Programação Mobile, POO, Bases de Dados, Matemática Discreta e Competências de Comunicação. Deve respeitar os requisitos da unidade (uso de base de dados relacional, REST APIs, Android/Kotlin, Spring Boot, uso de Figma, GitHub, ClickUp, etc.).

**Objetivos do projeto (concretos):**

- Implementar a app IADEGO em Android (Kotlin + Jetpack Compose).  
- Criar um backend REST em Spring Boot com BD relacional (MySQL/PostgreSQL).  
- Permitir reservar lanches, gerar QR temporário, gerir filas e localizações.  
- Fornecer GPS interno para encontrar salas.  
- Garantir dados fictícios (não usar dados reais).  
- Produzir documentação: diagrama de classes, modelo ER, documentação REST, mockups, Gantt.

---

## Público-alvo

- Estudantes do IADE (primário).  
- Funcionários do campus (bar, atendimento).  
- Visitantes ocasionais (secundário).

---

## Funcionalidades (conforme poster)

- Escolher produto (menu de bar: sanduíche, bolo, café, etc.).  
- Reserva de lanche em tempo real (botão **Reserve**).  
- Geração de QR Code para levantamento (válido 10 minutos).  
- GPS para encontrar salas e locais no campus.  
- Notificações de lembrete (pedido pronto / aviso de sala).  
- Visualização de saldo/preço (ex.: Muffin €1,00).  
- Interface simples tipo poster (fluxo rápido).

---

## Requisitos Funcionais e Não Funcionais

### Requisitos Funcionais (RF)
RF1. O sistema deve permitir que um estudante faça login (ou use modo convidado).  
RF2. O utilizador pode navegar no menu de lanches e selecionar produtos.  
RF3. O utilizador pode reservar um lanche e confirmar pagamento (simulado / offline).  
RF4. Após reserva, o sistema gera um QR Code associado ao pedido (validade 10 min).  
RF5. O bar valida o QR para entrega do pedido.  
RF6. O sistema disponibiliza GPS interno para localizar salas e marcar rota.  
RF7. O sistema envia notificações (pedido pronto / reminder aula).

### Requisitos Não Funcionais (RNF)
RNF1. Aplicação Android compatível com Android 9+.  
RNF2. Comunicação backend via REST (Spring Boot).  
RNF3. Base de dados relacional (MySQL ou PostgreSQL).  
RNF4. API e dados com autenticação e tratamento básico de privacidade (RGPD — dados fictícios).  
RNF5. Performance: geração de QR e resposta de reserva em < 3s em condições normais de rede campus.  
RNF6. QR Code válido por 10 minutos (expiração automática).  
RNF7. Interface responsiva e acessível (contraste, tamanhos).

---

## Modelo do Domínio (ER) — visão textual

**Entidades principais:**

- **User (Aluno)**: id, nome, email (fictício), curso, turma.  
- **Product (Produto do Bar)**: id, nome, descrição, preço, disponibilidade.  
- **Order (Pedido)**: id, user_id, estado (reservado / pronto / levantado), total, created_at.  
- **OrderItem**: id, order_id, product_id, quantity, price.  
- **QRCode**: id, order_id, code_value, issued_at, expires_at, used_flag.  
- **Room (Sala/Local)**: id, nome, piso, coords_internas.  
- **Notification**: id, user_id, type, message, created_at, read_flag.

(Relacionamentos: User 1..* Orders; Order 1..* OrderItems; Order 1..1 QRCode; Room usada para GPS/rotas.)

---

## Guiões de Teste (mín. 3)

### Guião 1 — Reservar um lanche e levantar com QR
1. Abrir app IADEGO.  
2. Entrar em “Menu” → escolher “Chicken Sandwich”.  
3. Clicar em **Reserve**.  
4. Confirmar reserva. O backend cria pedido e responde com QR Code.  
5. Verificar notificação “Pedido pronto” (simulado).  
6. Ir ao bar e mostrar QR. Operador valida QR (mobile/scanner).  
7. Pedido marcado como “levantado” no sistema.  
**Critério de sucesso:** QR validado e pedido marcado como levantado; QR invalida após uso.

### Guião 2 — QR expira após 10 minutos
1. Reservar um lanche (como Guião 1).  
2. Aguardar 11 minutos (simulação / avanço de tempo nos testes).  
3. Tentar validar QR no bar.  
**Critério de sucesso:** QR rejeitado por expirado; pedido mantém estado “reservado” e notifica utilizador para nova reserva.

### Guião 3 — Encontrar sala com GPS interno
1. Abrir app IADEGO.  
2. Ir à opção “Localizar Sala”.  
3. Inserir sala destino (ex.: “SALA B203”).  
4. Seguir instruções/rota interna até destino.  
**Critério de sucesso:** App orienta o utilizador até coordenadas internas correspondentes à sala.

---

## Casos de Utilização

### Caso de Utilização Core — “Reservar e Levantar Lanche”  
**Ator primário:** Estudante  
**Pré-condição:** Utilizador na app, produtos disponíveis.  
**Fluxo principal:**  
1. Selecionar produto.  
2. Confirmar reserva.  
3. Backend cria pedido e gera QR (expires_at = now + 10min).  
4. Notificação de confirmação é enviada.  
5. Utilizador apresenta QR no bar; operador valida; pedido entregue.  
**Fluxo alternativo:** Pagamento falha → cancelar pedido / notificar.  
**Pós-condição:** Pedido entregue / QR marcado como usado.

### Caso de Utilização 2 — “Localizar Sala (GPS interno)”  
**Ator:** Estudante  
**Resumo:** GPS interno guia o aluno até a sala indicada.

### Caso de Utilização 3 — “Notificações de Lembrete”  
**Ator:** Estudante  
**Resumo:** App envia lembretes de pedidos prontos e avisos de tempo para próxima aula.

---

## Plano de Trabalho, Project Charter & WBS (resumo)

**Fases principais (milestones):**

1. **Planeamento e Proposta** (semana 1–2)  
   - Definição do escopo, pesquisa, mockups iniciais (Figma), diagrama de domínio.  
2. **Protótipo (MVP)** (semanas 3–6)  
   - App Android: UI de menu, reserva, QR display.  
   - Backend básico: endpoints reserva, geração QR.  
   - BD com dados fictícios.  
3. **Desenvolvimento / Integração** (semanas 7–10)  
   - GPS interno, notificações, fluxo bar (validação QR).  
   - Documentação REST, diagrama de classes.  
4. **Testes e Ajustes** (semanas 11–12)  
   - Testes unitários, integração, correções.  
5. **Entrega Final** (semana 13)  
   - Relatório, poster, vídeo promo, apresentação.

**WBS (tarefa → responsável → duração estimada):**

- WBS-1: Documentação inicial e proposta — 5 dias (Team)  
- WBS-2: Design UI / Figma — 6 dias (David/Francisco)  
- WBS-3: Backend REST (Spring Boot) — 10 dias (Yosvany)  
- WBS-4: Mobile App (Kotlin / Compose) — 12 dias (Vivandro/Francisco)  
- WBS-5: BD (MySQL) e integração — 6 dias (Yosvany)  
- WBS-6: Testes e validação — 6 dias (Team)  
- WBS-7: Preparação Poster & Vídeo — 4 dias (Team)  

> **Gantt:** inserir/expor gráfico em `documents/primeira_entrega/gantt/gantt.pdf`. Incluir marcos: 1.ª entrega (versão do relatório e poster), entregas intermédias conforme brief.

---

## Requisitos Técnicos / Ferramentas Obrigatórias

- **Front-end Mobile:** Kotlin + Jetpack Compose (Android Studio).  
- **Back-end:** Java + Spring Boot (REST).  
- **BD:** MySQL ou PostgreSQL (relacional).  
- **Versionamento:** GitHub (repositório público/privado conforme regras).  
- **Gestão de projeto:** ClickUp.  
- **Comunicação:** Discord.  
- **Mockups:** Figma (obrigatório).  
- **Dados de teste:** fictícios (não usar dados reais).  
- **Documentação adicional:** diagrama de classes, modelo ER, doc REST.

---

## Entregas e Datas (conforme Briefing / 1.ª Entrega)

- **Constituição dos Grupos:** 1.ª aula (limite 1.ª semana).  
- **1.ª Entrega (4.ª semana / submissão final na 5.ª semana):**  
  - **Data submissão (exemplo no brief):** domingo, 05/10/2025 às 23:59.  
  - Conteúdos obrigatórios para a 1.ª Entrega: proposta, nome do projeto, enquadramento, pesquisa/contexto, objetivos, público-alvo, pesquisa sobre outras apps, pelo menos 3 guiões de teste, 1 caso de utilização "core" + 2 casos adicionais, plano de trabalhos, Project Charter & WBS, requisitos func./não-func., modelo do domínio, mockups/interfaces, Gantt.  
- **Poster:** entrega junto da 1.ª Entrega.  
- **Vídeo promocional:** 1 minuto, a entregar em entregas posteriores conforme briefing.

---

## Mockups / Interfaces / Figma

- Mockups iniciais (inspirados no poster) devem ser feitos em Figma e link adicionada aqui.  
- Interfaces essenciais: ecrã de menu/seleção, ecrã de reserva/confirm, ecrã com QR Code, ecrã de GPS/rotas, ecrã de notificações.

---

## Documentação REST (resumo mínimo a incluir)

- **POST /orders** — criar reserva (body: user_id, items).  
- **GET /orders/{id}/qrcode** — obter QR (imagem / token).  
- **POST /qrcode/validate** — validar QR (operador do bar).  
- **GET /rooms** — listar salas / coordenadas internas.  
- **POST /notifications** — enviar notificações push (simulado).

(Descrever cada endpoint com parâmetros, respostas e códigos HTTP na documentação final.)

---

## Conclusão / Benefícios (conforme poster)

**Para estudantes:** mais tempo, menos stress — evitar filas e não perder aulas ou lanche.  
**Para o campus:** melhor gestão do fluxo de pessoas, menos filas, maior organização do bar e das salas.
