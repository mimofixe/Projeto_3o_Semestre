# Iade Go - [IADE](https://www.iade.europeia.pt/) - [UE](https://www.europeia.pt/)


**Universidade:** [Universidade Europeia](https://www.europeia.pt/)
**Faculdade:** [IADE - Faculdade de Design, Tecnologia e Comunicação](https://www.iade.europeia.pt/)
**Repositório:** [think-toilet](https://github.com/nycocado/think-toilet)
**Curso:** Engenharia Informática

## Índice

* [Elementos do Grupo](#elementos-do-grupo)
* [Poster](#poster)
* [Palavras-Chave](#palavras-chave)
* [Descrição](#descrição)

  * [Motivação](#motivação)
  * [Objetivos](#objetivos)
* [Público-Alvo](#público-alvo)
* [Pesquisa de Mercado](#pesquisa-de-mercado)
* [Guiões de Teste](#guiões-de-teste)
* [Plano de Trabalho](#plano-de-trabalho)
* [Descrição da Solução](#descrição-da-solução)
* [Enquadramento das Unidades Curriculares](#enquadramento-das-unidades-curriculares)
* [Requisitos Técnicos](#requisitos-técnicos)
* [Arquitetura da Solução](#arquitetura-da-solução)
* [Tecnologias](#tecnologias)
* [Planificação](#planificação)
* [Interface](#interface)
* [Conclusão](#conclusão)
* [Bibliografia](#bibliografia)

## Elementos do Grupo:

* 20230331 - David Bação
* 202301001 - Francisco Lourinho
* 20241805 - Vivandro Kambaza
* 20230853 - Yosvany Nunes

## Poster

![Poster do Projeto](Imagem%20WhatsApp%202025-09-30%20às%2020.04.02_55d5b6dc.jpg)

## Palavras-Chave

Localizador; Avaliação; Sanitários; Casa de banho; Público; Privada; QR Code; Reservas; Salas; Bar; GPS; IADE; Infraestrutura; Mobile; App; Interativo; Experiência do Estudante.

## Descrição

O **Iade GO** é uma aplicação móvel que combina duas vertentes:

1. **Iade Go versão pública):** encontrar casas de banho limpas e acessíveis em qualquer local, com avaliações, sugestões e integração com Google Maps.
2. **Iade Go (versão campus):** controlar e otimizar a infraestrutura da faculdade IADE, oferecendo:

   * Disponibilidade de casas de banho (com acesso via QR code).
   * Visualização e marcação de salas como livres/ocupadas.
   * Controle de climatização e luzes via Bluetooth.
   * Reserva e pagamento (na app ou presencial) de refeições no bar.
   * GPS interno para guiar o aluno até a sala da próxima aula.

Dessa forma, o projeto não só resolve problemas comuns em espaços públicos, mas também fornece uma solução personalizada para o ambiente académico do IADE.

### Motivação

A ideia surgiu após conversas com professores sobre melhorias na infraestrutura. Muitos sistemas existentes (como reserva de salas, mapas internos ou gestão de recursos) são fragmentados ou inexistentes, causando frustração nos estudantes. Aliando essa necessidade com a inspiração do **Think Toilet** (banheiros públicos), criamos um projeto híbrido: útil no dia a dia e escalável para além da faculdade.

### Objetivos

* Facilitar a busca de casas de banho limpas e próximas (Think Toilet).
* Melhorar a experiência do estudante no campus IADE.
* Disponibilizar reservas rápidas de comida e salas.
* Integrar controle ambiental (luz/ar condicionado) de forma simples.
* Criar um sistema de GPS interno para navegação entre salas.
* Incentivar feedback dos utilizadores para manter dados sempre atualizados.

## Público-Alvo

* Estudantes e professores do **IADE** (uso interno da infraestrutura).
* Trabalhadores em trânsito, turistas e público em geral (uso externo do Think Toilet).
* Pessoas com necessidades de acessibilidade.

## Pesquisa de Mercado

Foram analisadas aplicações existentes para localização de casas de banho, como **Where is the Toilet**, **Berlin Toilet**, **Flush** e **Where is Public Toilet**. Todas apresentam limitações em termos de interface, funcionalidades e atualizações. O **Think Toilet** propõe-se a melhorar esses aspetos.

Além disso, dentro do contexto académico, existem falhas em apps de gestão interna de campus, o que cria espaço para o **Infra IADE**.

## Guiões de Teste

1. **Localizar casa de banho próxima.**
2. **Dar feedback sobre a casa de banho.**
3. **Pesquisar uma casa de banho específica.**
4. **Reservar sala vazia.**
5. **Controlar luz/ar condicionado via Bluetooth.**
6. **Reservar comida no bar.**
7. **Seguir rota GPS até à sala da próxima aula.**

## Plano de Trabalho

| **Fase**                       | **Descrição**                                                              | **Prazo**  |
| ------------------------------ | -------------------------------------------------------------------------- | ---------- |
| 1. Planejamento e Prototipação | Definição do escopo, protótipos no Figma.                                  | 20/10/2024 |
| 2. Protótipo                   | Implementação inicial em Kotlin/Compose, backend em Spring Boot, DB MySQL. | 24/11/2024 |
| 3. Desenvolvimento Final       | Funcionalidades completas: banheiros, reservas, GPS, controlo de infra.    | 12/01/2025 |
| 4. Testes                      | Unitários e integração, feedback de utilizadores.                          | 12/01/2025 |
| 5. Documentação                | Relatório final e README atualizado.                                       | 12/01/2025 |

## Descrição da Solução

O sistema une **localização de banheiros públicos** com **gestão interna do campus IADE**, tudo dentro da mesma aplicação. Utiliza:

* App em Kotlin (Jetpack Compose).
* Backend em Java (Spring Boot).
* Base de dados MySQL.
* Integração com Google Maps + GPS interno.
* Comunicação por Bluetooth para dispositivos de sala.

## Enquadramento das Unidades Curriculares

* **Programação de Dispositivos Móveis:** front-end Android em Kotlin.
* **POO:** backend em Java + Spring Boot.
* **Bases de Dados:** modelagem em MySQL.
* **Matemática Discreta:** lógica de rotas, reservas e algoritmos internos.
* **Projeto de Desenvolvimento Móvel:** planeamento e gestão.
* **Competências Comunicacionais:** interação com stakeholders e usabilidade.

## Requisitos Técnicos

### Funcionais

* Buscar casas de banho e salas livres.
* Avaliar banheiros.
* Reservar salas e comida.
* Controlar iluminação e climatização.
* GPS interno para localização de salas.
* Denúncia de locais/comentários inadequados.

### Não Funcionais

* Interface intuitiva.
* Criptografia de dados.
* Compatível com Android 9+.
* Integração com Google Maps API.
* Comunicação eficiente entre front-end, back-end e DB.

## Arquitetura da Solução

* **Front-end:** App Android em Kotlin/Compose.
* **Back-end:** Spring Boot (REST APIs).
* **DB:** MySQL.
* **Integrações:** Google Maps API, GPS interno, Bluetooth.

## Tecnologias

* Kotlin + Jetpack Compose.
* Java + Spring Boot.
* MySQL.
* Google Maps API.
* Figma para prototipação.

## Planificação

[Gráfico de Gantt](documents/primeira_entrega/gantt/gantt.pdf)
[ClickUp](https://app.clickup.com/9012385337/v/s/90121717706)

## Interface

Inclui telas de:

* Mapa de casas de banho.
* Avaliações.
* Reservas de salas.
* Controle de luz/ar condicionado.
* Reserva de comida.
* GPS interno.

## Conclusão

O projeto **Think Toilet & Infra IADE** alia utilidade prática (localização de casas de banho públicas) com inovação no ambiente académico (gestão da infraestrutura do IADE). Assim, oferece uma aplicação robusta, útil e escalável, capaz de melhorar significativamente a experiência dos estudantes e ainda servir como modelo para outras instituições.

## Bibliografia

* [Spreadshit - Exame](https://exame.com/pop/spreadshit-planilha-avalia-banheiros-empresas/)
* [Where is the Toilet](https://play.google.com/store/apps/details?id=com.iisrl.toilet.star.toilet_star)
* [Berlin Toilet](https://play.google.com/store/apps/details?id=com.futurice.berlintoiletapp)
* [Flush](https://play.google.com/store/apps/details?id=toilet.samruston.com.toilet)
* [Where is Public Toilet](https://play.google.com/store/apps/details?id=sfcapital.publictoiletinsouthaustralia)
* [Kotlin](https://kotlinlang.org)
* [Jetpack Compose](https://developer.android.com/compose)
* [Spring Boot](https://spring.io)
* [MySQL](https://www.mysql.com/)
* [Google Maps API](https://developers.google.com/maps)
* [Figma](https://www.figma.com/)
