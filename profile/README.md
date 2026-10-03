<img src="https://capsule-render.vercel.app/api?type=waving&color=0:360082,100:6A00FF&height=140&section=header&animation=fadeIn" width="100%" alt="" />

<div align="center">

<img src="https://raw.githubusercontent.com/InventraTech/.github/main/profile/assets/hero.svg" alt="Inventra — precisão digital na gestão de estoques de alimentos" width="100%" />

<br /><br />

<a href="#sobre-o-projeto">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=20&duration=3000&pause=800&color=6A00FF&center=true&vCenter=true&width=640&lines=Menos+desperd%C3%ADcio%2C+mais+controle.;Validades+monitoradas+em+tempo+real.;Decis%C3%B5es+de+compra+guiadas+por+dados.;IA+a+servi%C3%A7o+da+cozinha.;Alinhado+ao+ODS+12+da+ONU." alt="Menos desperdício, mais controle." />
</a>

<br /><br />

<a href="https://brasil.un.org/pt-br/sdgs/12"><img src="https://img.shields.io/badge/ODS_12-Consumo_e_Produção_Responsáveis-ECC506?style=for-the-badge&logo=unitednations&logoColor=360082&labelColor=FFDE3B" alt="ODS 12" /></a>
<img src="https://img.shields.io/badge/Ensino_Médio_Técnico-2026-6A00FF?style=for-the-badge&logo=bookstack&logoColor=white&labelColor=360082" alt="Ensino Médio Técnico 2026" />
<a href="https://github.com/orgs/InventraTech/repositories"><img src="https://img.shields.io/badge/Status-Em_desenvolvimento-6A00FF?style=for-the-badge&logo=githubactions&logoColor=white&labelColor=360082" alt="Em desenvolvimento" /></a>

<br /><br />

<b>
<a href="#sobre-o-projeto">Sobre</a> ·
<a href="#funcionalidades">Funcionalidades</a> ·
<a href="#ods-12--consumo-e-produção-responsáveis">ODS 12</a> ·
<a href="#arquitetura">Arquitetura</a> ·
<a href="#tecnologias">Tecnologias</a> ·
<a href="#repositórios">Repositórios</a> ·
<a href="#equipe">Equipe</a>
</b>

</div>

<br />

## Sobre o projeto

**Inventra** é um projeto interdisciplinar de Ensino Médio técnico, desenvolvido em 2026 e alinhado ao **ODS 12 — Consumo e Produção Responsáveis** da Agenda 2030 da ONU. A proposta é levar **precisão digital à gestão de estoques de alimentos**, reduzindo o desperdício em restaurantes, cozinhas industriais e outras operações gastronômicas.

<table>
<tr>
<td width="50%" valign="top">

### O problema

Muitas operações de alimentação ainda controlam o estoque de forma informal — por memória, planilhas desatualizadas ou "olhômetro". Isso torna a conferência lenta, reduz a rastreabilidade e aumenta o risco de **compras mal planejadas**, **insumos vencidos** e **desperdício financeiro**.

</td>
<td width="50%" valign="top">

### A solução

Um ecossistema digital de ponta a ponta para **registrar, acompanhar e analisar** o estoque, com indicadores claros e um assistente de IA (**IAI**) que apoia estoquistas, compradores e supervisores no dia a dia.

</td>
</tr>
</table>

**Público-alvo:** equipes de estoque, gerentes, proprietários e compradores de restaurantes e outros serviços de alimentação.

## Funcionalidades

<table>
<tr>
<td align="center" width="25%"><b>Cadastro inteligente</b><br /><sub>Por foto/OCR ou manual</sub></td>
<td align="center" width="25%"><b>Controle de estoque</b><br /><sub>Quantidades e validades</sub></td>
<td align="center" width="25%"><b>Alertas</b><br /><sub>Avisos de vencimento</sub></td>
<td align="center" width="25%"><b>Dashboard</b><br /><sub>Indicadores da operação</sub></td>
</tr>
<tr>
<td align="center"><b>Requisições</b><br /><sub>Pedidos de compra</sub></td>
<td align="center"><b>Histórico</b><br /><sub>Movimentações rastreáveis</sub></td>
<td align="center"><b>IAI</b><br /><sub>Assistente multiagente</sub></td>
<td align="center"><b>Web e mobile</b><br /><sub>Acesso em qualquer lugar</sub></td>
</tr>
</table>

> [!NOTE]
> As telas do produto existem hoje como protótipo de alta fidelidade, com fluxos e regras ainda em especificação e implementação pelas frentes listadas abaixo.

## ODS 12 — Consumo e Produção Responsáveis

| Meta | Descrição | Como o Inventra contribui |
|:-:|---|---|
| ![12.3](https://img.shields.io/badge/12.3-ECC506?style=flat-square) | Redução do desperdício de alimentos | **Foco principal:** evitar que insumos vençam no estoque |
| ![12.5](https://img.shields.io/badge/12.5-ECC506?style=flat-square) | Redução da geração de resíduos | Menos descarte de alimentos e dos recursos usados para produzi-los |
| ![12.8](https://img.shields.io/badge/12.8-ECC506?style=flat-square) | Conscientização para o consumo responsável | Métricas e alertas incentivam uma cultura de gestão consciente |

## Arquitetura

```mermaid
flowchart LR
    subgraph Clientes
        WEB["Web<br/>React + TypeScript"]
        MOB["Mobile<br/>Kotlin"]
    end

    subgraph Backend
        API["API Spring<br/>Redis + Neo4j"]
        MAPI["API Spring<br/>MongoDB"]
        IA["IAI<br/>Python · multiagente"]
    end

    subgraph Dados
        PG[("PostgreSQL")]
        RD[("Redis")]
        NJ[("Neo4j")]
        MG[("MongoDB")]
    end

    WEB --> API
    MOB --> API
    WEB --> MAPI
    WEB --> IA
    API --> PG
    API --> RD
    API --> NJ
    MAPI --> MG

    classDef cliente fill:#6A00FF,stroke:#360082,color:#ffffff
    classDef servico fill:#360082,stroke:#6A00FF,color:#ffffff
    classDef dado fill:#FFDE3B,stroke:#ECC506,color:#360082
    class WEB,MOB cliente
    class API,MAPI,IA servico
    class PG,RD,NJ,MG dado
```

<sub>Visão geral das frentes de desenvolvimento. A infraestrutura (Docker e CI/CD com GitHub Actions) é mantida pela frente de Operações Ágeis.</sub>

## Tecnologias

<div align="center">

<img src="https://skillicons.dev/icons?i=react,ts,tailwind,java,spring,kotlin,python&perline=7" alt="Linguagens e frameworks" />
<br /><br />
<img src="https://skillicons.dev/icons?i=postgres,mongodb,redis,docker,githubactions,git,github&perline=7" alt="Dados e infraestrutura" />
<br /><br />
<img src="https://img.shields.io/badge/Neo4j-4581C3?style=for-the-badge&logo=neo4j&logoColor=white" alt="Neo4j" />
<img src="https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white" alt="Jupyter" />

</div>

## Repositórios

### 2º ano

| Repositório | Frente | Descrição | Atividade |
|---|---|---|---|
| [**data-modeling**](https://github.com/InventraTech/inventra-data-modeling-2) | Arte e Modelagem de Dados | Modelagem e scripts do banco relacional (PostgreSQL) | ![](https://img.shields.io/github/last-commit/InventraTech/inventra-data-modeling-2?style=flat-square&label=&color=6A00FF) |
| [**spring-redis-neo4j**](https://github.com/InventraTech/inventra-development-spring-redis-neo4j-2) | Desenvolvimento | API em Spring, com Redis e Neo4j | ![](https://img.shields.io/github/last-commit/InventraTech/inventra-development-spring-redis-neo4j-2?style=flat-square&label=&color=6A00FF) |
| [**development-mongo**](https://github.com/InventraTech/inventra-development-mongo-2) | Desenvolvimento | API em Spring para o banco não relacional MongoDB | ![](https://img.shields.io/github/last-commit/InventraTech/inventra-development-mongo-2?style=flat-square&label=&color=6A00FF) |
| [**dynamic-applications**](https://github.com/InventraTech/inventra-dynamic-applications-2) | Aplicações Dinâmicas | Front-end em React, TypeScript e Tailwind CSS | ![](https://img.shields.io/github/last-commit/InventraTech/inventra-dynamic-applications-2?style=flat-square&label=&color=6A00FF) |
| [**artificial-intelligence**](https://github.com/InventraTech/inventra-artificial-intelligence-2) | Inteligência Artificial | Sistema multiagente para estoquistas, compradores e supervisores | ![](https://img.shields.io/github/last-commit/InventraTech/inventra-artificial-intelligence-2?style=flat-square&label=&color=6A00FF) |
| [**mobile-development**](https://github.com/InventraTech/inventra-mobile-development-2) | Desenvolvimento Mobile | Aplicativo mobile do Inventra | ![](https://img.shields.io/github/last-commit/InventraTech/inventra-mobile-development-2?style=flat-square&label=&color=6A00FF) |
| [**agile-operations**](https://github.com/InventraTech/inventra-agile-operations-development-2) | Operações Ágeis | Automação, infraestrutura, conteinerização e implantação | ![](https://img.shields.io/github/last-commit/InventraTech/inventra-agile-operations-development-2?style=flat-square&label=&color=6A00FF) |
| [**software-engineering**](https://github.com/InventraTech/inventra-software-engineering-2) | Engenharia e Qualidade de Software | Levantamento e documentação de requisitos | ![](https://img.shields.io/github/last-commit/InventraTech/inventra-software-engineering-2?style=flat-square&label=&color=6A00FF) |

<details>
<summary><b>1º ano</b> — clique para expandir</summary>
<br />

| Repositório | Disciplina | Descrição |
|---|---|---|
| [**Inventra1-BD**](https://github.com/InventraTech/Inventra1-BD) | Banco de Dados | Projetos de banco de dados do 1º ano |
| [**inventra1-poo**](https://github.com/InventraTech/inventra1-poo) | Programação Orientada a Objetos | Demandas de POO do 1º ano |
| [**Inventra1-POO-LPR**](https://github.com/InventraTech/Inventra1-POO-LPR) | POO / LPR | Projetos de POO/LPR do 1º ano |
| [**Inventra1-HTML**](https://github.com/InventraTech/Inventra1-HTML) | HTML | Projetos de HTML do 1º ano |

</details>

<sub>O repositório [.github](https://github.com/InventraTech/.github) reúne as configurações padrão da organização: README de perfil, template de Pull Request e workflows de CI/CD reutilizáveis.</sub>

## Equipe

<div align="center">

### 2º ano

<table>
<tr>
<td align="center" width="150">
<a href="https://github.com/dvarakaki"><img src="https://github.com/dvarakaki.png?size=200" width="100" alt="Davi Arakaki" /><br /><b>Davi Arakaki</b></a><br /><sub>@dvarakaki</sub>
</td>
<td align="center" width="150">
<a href="https://github.com/EduardoPassosdeQueiroz"><img src="https://github.com/EduardoPassosdeQueiroz.png?size=200" width="100" alt="Eduardo Passos" /><br /><b>Eduardo Passos</b></a><br /><sub>@EduardoPassosdeQueiroz</sub>
</td>
<td align="center" width="150">
<a href="https://github.com/FelipeKogake"><img src="https://github.com/FelipeKogake.png?size=200" width="100" alt="Felipe Kogake" /><br /><b>Felipe Kogake</b></a><br /><sub>@FelipeKogake</sub>
</td>
</tr>
<tr>
<td align="center" width="150">
<a href="https://github.com/JonesPrado"><img src="https://github.com/JonesPrado.png?size=200" width="100" alt="João Victor Prado" /><br /><b>João Victor Prado</b></a><br /><sub>@JonesPrado</sub>
</td>
<td align="center" width="150">
<a href="https://github.com/joohnyxxz"><img src="https://github.com/joohnyxxz.png?size=200" width="100" alt="João Vitor Maldonado" /><br /><b>João Vitor Maldonado</b></a><br /><sub>@joohnyxxz</sub>
</td>
<td align="center" width="150">
<a href="https://github.com/RafaelPassosQueiroz"><img src="https://github.com/RafaelPassosQueiroz.png?size=200" width="100" alt="Rafael Passos" /><br /><b>Rafael Passos</b></a><br /><sub>@RafaelPassosQueiroz</sub>
</td>
</tr>
</table>

### 1º ano

<table>
<tr>
<td align="center" width="150">
<a href="https://github.com/DelJorgeLlanos"><img src="https://github.com/DelJorgeLlanos.png?size=200" width="100" alt="Jorge Llanos" /><br /><b>Jorge Llanos</b></a><br /><sub>@DelJorgeLlanos</sub>
</td>
<td align="center" width="150">
<a href="https://github.com/dudaanjos103-cloud"><img src="https://github.com/dudaanjos103-cloud.png?size=200" width="100" alt="Maria Eduarda Anjos" /><br /><b>Maria Eduarda Anjos</b></a><br /><sub>@dudaanjos103-cloud</sub>
</td>
<td align="center" width="150">
<a href="https://github.com/erickaraga0"><img src="https://github.com/erickaraga0.png?size=200" width="100" alt="Erick Aragão" /><br /><b>Erick Aragão</b></a><br /><sub>@erickaraga0</sub>
</td>
</tr>
<tr>
<td align="center" width="150">
<a href="https://github.com/GabrielFlavinho"><img src="https://github.com/GabrielFlavinho.png?size=200" width="100" alt="Gabriel Favrin" /><br /><b>Gabriel Favrin</b></a><br /><sub>@GabrielFlavinho</sub>
</td>
<td align="center" width="150">
<a href="https://github.com/stellacostaf"><img src="https://github.com/stellacostaf.png?size=200" width="100" alt="Stella Costa" /><br /><b>Stella Costa</b></a><br /><sub>@stellacostaf</sub>
</td>
<td align="center" width="150"></td>
</tr>
</table>

</div>

<br />

<div align="center">

<sub>Desenvolvido pela equipe <b>Inventra</b> · Alinhado à <a href="https://brasil.un.org/pt-br/sdgs/12">Agenda 2030 da ONU</a></sub>

</div>

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:6A00FF,100:360082&height=120&section=footer" width="100%" alt="" />
