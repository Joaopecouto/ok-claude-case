<h1 align="center">Ok, Claude</h1>

<p align="center">
  Agenda pessoal desktop com assistente de IA.<br>
  <sub><i>Desktop personal planner with an AI assistant.</i></sub>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Tauri_2-24C8D8?style=flat-square&logo=tauri&logoColor=white">
  <img src="https://img.shields.io/badge/Rust-000000?style=flat-square&logo=rust&logoColor=white">
  <img src="https://img.shields.io/badge/React_19-20232A?style=flat-square&logo=react&logoColor=61DAFB">
  <img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white">
  <img src="https://img.shields.io/badge/SQLite-003B57?style=flat-square&logo=sqlite&logoColor=white">
  <img src="https://img.shields.io/badge/Claude_API-191919?style=flat-square&logo=anthropic&logoColor=white">
</p>

> Case study de um projeto em desenvolvimento. O código é privado. · <i>Work-in-progress case study. Source code is private.</i>

## O que é · What it is

Agenda desktop para Windows, de uso pessoal, com um módulo de assistente que chama a **API da Anthropic**. A regra de produto para a IA é simples: ela não inventa. Informação de fora do app só aparece com fonte e link.

## Decisões técnicas · Technical decisions

- **Chave da API no Gerenciador de Credenciais do Windows**, nunca em arquivo, e segredos passam por redação antes de qualquer log.
- **SQLite** com migrações numeradas e cópia antes de cada uma, modo WAL, backup diário e abertura do backup quando o banco corrompe.
- **Contrato único entre Rust e TypeScript:** os tipos dos comandos são gerados a partir do Rust, e uma só suíte de contrato vale para o backend real e para o falso do `invoke`.
- **Voz em fase de medição:** escuta local com palavra de ativação e transcrição em streaming estão sendo medidas (CPU, RAM, atraso, erro em português) antes de entrar no produto.

## Como foi construído · How it was built

Desenvolvimento com **subagentes do Claude Code em worktrees isolados**, hooks de git, de testes e de padrões, e CI em toda branch. Foram **333 commits em 6 dias** (29/10 a 03/11/2026) e **1.031 testes** de TypeScript passando em 05/11/2026.

<sub>Contato · Contact: <a href="mailto:joaopecouto77@gmail.com">joaopecouto77@gmail.com</a> · <a href="https://joaocouto.alcetus.com">joaocouto.alcetus.com</a></sub>
