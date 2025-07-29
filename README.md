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

## Sobre o Projeto

Clarify é uma aplicação web fullstack (SaaS) que criei do zero para resolver um problema real: a complexidade do gerenciamento financeiro compartilhado entre casais, famílias e grupos.

---
![WhatsApp Image 2025-07-29 at 11 10 30](https://github.com/user-attachments/assets/bc31dc0b-7191-4b06-b971-f2f360abcd3a)
---


## Status do Projeto

Em desenvolvimento

---

## Meu Papel

Arquiteto e Desenvolvedor Fullstack (Solo)

---

## Código-Fonte

Privado / Proprietário  
Este repositório serve como uma vitrine técnica. O código não é público, mas a arquitetura, decisões técnicas e funcionalidades estão documentadas aqui para fins de portfólio.

---

<h2 id="problema">Problema</h2>

Grupos que compartilham finanças (casais, famílias, colegas de república) geralmente usam planilhas confusas, anotações ou apenas a memória. Isso causa:

- Estresse financeiro  
- Falta de clareza  
- Dificuldade em atingir metas comuns  

---

<h2 id="solucao">Solução: Clarify</h2>
<img width="1024" height="1024" alt="mascote_feliz" src="https://github.com/user-attachments/assets/45b89ae9-311c-4d5e-9256-61df71b87165" />


Clarify centraliza a gestão financeira compartilhada em uma interface intuitiva com:

- Carteiras em grupo  
- Metas coletivas  
- Adição de transações com IA  
- Relatórios e painéis colaborativos  

---

<h2 id="arquitetura">Arquitetura Técnica</h2>

A aplicação foi construída com uma arquitetura desacoplada:

- Frontend em React  
- Backend em FastAPI (API RESTful)  
- Banco de dados relacional com PostgreSQL  
- Integrações com Mercado Pago e Google Gemini  

---

<h2 id="funcionalidades">Funcionalidades</h2>

<table>
  <thead>
    <tr>
      <th>Funcionalidade</th>
      <th>Descrição</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Autenticação Segura</td>
      <td>Login com JWT e controle de perfis (cliente / colaborador)</td>
    </tr>
    <tr>
      <td>Proteção Anti-Fraude</td>
      <td>Rate limiting por IP e bloqueio após tentativas de login falhas</td>
    </tr>
    <tr>
      <td>Modelagem Avançada</td>
      <td>ORM com SQLAlchemy e relacionamentos complexos</td>
    </tr>
    <tr>
      <td>Assinaturas</td>
      <td>Integração completa com Mercado Pago, incluindo Webhooks</td>
    </tr>
    <tr>
      <td>Inteligência Artificial</td>
      <td>Interpretação de transações via linguagem natural com Gemini</td>
    </tr>
    <tr>
      <td>Painel Administrativo</td>
      <td>Permissões diferenciadas por cargo (Admin, Suporte)</td>
    </tr>
    <tr>
      <td>Sanitização de Inputs</td>
      <td>Prevenção contra XSS em todos os dados inseridos</td>
    </tr>
  </tbody>
</table>

---

<h2 id="tecnologias">Tecnologias Utilizadas</h2>

<table>
  <thead>
    <tr>
      <th>Categoria</th>
      <th>Tecnologias</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Backend</td>
      <td>Python, FastAPI, SQLAlchemy</td>
    </tr>
    <tr>
      <td>Frontend</td>
      <td>React, TailwindCSS, Axios</td>
    </tr>
    <tr>
      <td>Banco de Dados</td>
      <td>PostgreSQL</td>
    </tr>
    <tr>
      <td>APIs Externas</td>
      <td>Mercado Pago, Google Gemini</td>
    </tr>
  </tbody>
</table>

---

<h2 id="desafios">Desafios Técnicos e Soluções</h2>

<h4>Sistema de Permissões Flexível</h4>
<strong>Problema:</strong> Diferenciar múltiplos tipos de colaboradores (admin, suporte)  
<strong>Solução:</strong> O cargo é incluído no JWT. Dependências personalizadas no backend validam o acesso a cada rota crítica.

<h4>Proteção contra Credential Stuffing</h4>
<strong>Problema:</strong> Tentativas repetidas de login comprometem a segurança  
<strong>Solução:</strong> Rate limiting por IP, contador de tentativas e bloqueio temporário com cache em memória.

<h4>Assinaturas Concedidas por Admin</h4>
<strong>Problema:</strong> Assinaturas manuais geravam erro 404 na API do Mercado Pago  
<strong>Solução:</strong> O backend identifica essas assinaturas e define um campo especial que ajusta a exibição no frontend para evitar erros e melhorar a experiência.

---

## Agradecimentos

Obrigado por analisar meu projeto!  
Fico à disposição para discutir a arquitetura e as decisões técnicas com mais detalhes.

---


