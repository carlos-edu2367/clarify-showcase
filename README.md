<div align="center">
  <img src="https://placehold.co/1200x600/0f172a/3b82f6?text=Clarify&font=inter" alt="Clarify Dashboard" width="800"/>
  <h1><strong>Estudo de Caso: Clarify</strong></h1>
  <h3>SaaS de Gestão Financeira Colaborativa</h3>
  <p>
    <a href="#problema">Problema</a> •
    <a href="#solucao">Solução</a> •
    <a href="#demonstracao">Demonstração</a> •
    <a href="#arquitetura">Arquitetura</a> •
    <a href="#funcionalidades">Funcionalidades</a> •
    <a href="#tecnologias">Tecnologias</a> •
    <a href="#desafios">Desafios</a>
  </p>
</div>

---

<h2 id="sobre">📌 Sobre o Projeto</h2>

<p>
<strong>Clarify</strong> é uma aplicação web fullstack (SaaS) que criei do zero para resolver um problema real: a complexidade do gerenciamento financeiro compartilhado entre casais, famílias e grupos.
</p>

---

<h2>🚧 Status do Projeto</h2>

<p><strong>🚀 Em desenvolvimento</strong></p>

---

<h2>👨‍💻 Meu Papel</h2>

<p><strong>Arquiteto e Desenvolvedor Fullstack (Solo)</strong></p>

---

<h2>🔒 Código-Fonte</h2>

<p>
<strong>Privado / Proprietário</strong><br>
Este repositório serve como vitrine técnica. O código não é público, mas a arquitetura, decisões técnicas e funcionalidades estão documentadas.
</p>

---

<h2 id="problema">🎯 O Problema</h2>

<p>
Grupos que compartilham finanças (casais, famílias, colegas de república) geralmente usam planilhas confusas, anotações ou apenas "memória". Isso causa:
<ul>
  <li>Estresse financeiro</li>
  <li>Falta de clareza</li>
  <li>Dificuldade em atingir metas comuns</li>
</ul>
</p>

---

<h2 id="solucao">✨ A Solução: Clarify</h2>

<p>
Clarify centraliza a gestão financeira compartilhada em uma interface intuitiva, com:
<ul>
  <li>💼 Carteiras em grupo</li>
  <li>🎯 Metas coletivas</li>
  <li>🤖 Transações inteligentes com IA</li>
  <li>📊 Relatórios colaborativos</li>
</ul>
</p>

---

<h2 id="demonstracao">🎥 Demonstração em Vídeo</h2>

<p>
💡 <i>Dica: Grave um vídeo curto mostrando o fluxo principal: login, dashboard, IA, metas e painel de colaborador.</i><br>
🔗 <strong>[Assista à Demonstração (Link do YouTube/Vimeo)](#)</strong>
</p>

---

<h2 id="arquitetura">🏛️ Arquitetura Técnica</h2>

<p>
A aplicação foi construída com arquitetura desacoplada:
<ul>
  <li>Frontend: React</li>
  <li>Backend: FastAPI REST</li>
  <li>Banco de Dados: PostgreSQL</li>
  <li>Integrações: Mercado Pago (pagamentos), Google Gemini (IA)</li>
</ul>

💡 <i>Dica: Inclua aqui um diagrama (draw.io ou Excalidraw) explicando o fluxo Cliente → Frontend → API → DB</i>
</p>

---

<h2 id="funcionalidades">🚀 Funcionalidades Principais</h2>

<table>
  <tr><th>Funcionalidade</th><th>Descrição</th></tr>
  <tr><td>🔐 Autenticação Segura</td><td>Login com JWT e controle de perfis (cliente / colaborador)</td></tr>
  <tr><td>🛡️ Anti-Fraude</td><td>Rate limiting por IP e bloqueio após falhas no login</td></tr>
  <tr><td>📦 Modelagem Avançada</td><td>ORM SQLAlchemy com relacionamentos e tabelas auxiliares</td></tr>
  <tr><td>💳 Assinaturas</td><td>Integração completa com Mercado Pago + Webhooks</td></tr>
  <tr><td>🤖 IA com Gemini</td><td>Análise de transações em linguagem natural</td></tr>
  <tr><td>👥 Painel Administrativo</td><td>Permissões por cargo (ADM, Suporte)</td></tr>
  <tr><td>💧 Sanitização</td><td>Proteção contra XSS em todos os inputs</td></tr>
</table>

---

<h2 id="tecnologias">🛠️ Tecnologias Utilizadas</h2>

<table>
  <tr><th>Categoria</th><th>Tecnologias</th></tr>
  <tr><td>Backend</td><td>Python, FastAPI, SQLAlchemy</td></tr>
  <tr><td>Frontend</td><td>React, TailwindCSS, Axios</td></tr>
  <tr><td>Banco de Dados</td><td>PostgreSQL</td></tr>
  <tr><td>APIs Externas</td><td>Mercado Pago, Google Gemini</td></tr>
</table>

---

<h2 id="desafios">💡 Desafios Técnicos e Soluções</h2>

<h4>🧩 Sistema de Permissões Flexível</h4>
<p><strong>Problema:</strong> Diferenciar múltiplos tipos de colaboradores (ADM, suporte)<br>
<strong>Solução:</strong> Cargo inserido no JWT. Dependências em rotas FastAPI checam permissões dinamicamente.</p>

<h4>🔒 Proteção contra Credential Stuffing</h4>
<p><strong>Problema:</strong> Login exposto a força bruta<br>
<strong>Solução:</strong> Rate Limiting por IP + contador de tentativas → bloqueio automático.</p>

<h4>🤝 UX em Assinaturas Concedidas</h4>
<p><strong>Problema:</strong> Planos concedidos por admin causavam erro no Mercado Pago (404)<br>
<strong>Solução:</strong> Identificador especial para planos concedidos manualmente, com interface customizada no frontend.</p>

---

<h2>🙏 Agradecimentos</h2>

<p>Obrigado por dedicar seu tempo a este estudo de caso!<br>
Se quiser discutir mais sobre a arquitetura ou tiver feedback, estou à disposição 😄</p>
