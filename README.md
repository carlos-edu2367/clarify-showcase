<div align="center">
<img src="URL_DA_SUA_IMAGEM_DE_CAPA" alt="Clarify Dashboard" width="800"/>
<h1><strong>Estudo de Caso: Clarify</strong></h1>
<h3><strong>SaaS de Gestão Financeira Colaborativa</strong></h3>
<p>
<a href="#-o-problema">O Problema</a> •
<a href="#-a-solução-clarify">A Solução</a> •
<a href="#-arquitetura-técnica">Arquitetura</a> •
<a href="#-funcionalidades-principais">Funcionalidades</a> •
<a href="#-tecnologias-utilizadas">Tecnologias</a> •
<a href="#-desafios-técnicos-e-soluções">Desafios</a>
</p>
</div>

Clarify é uma aplicação web fullstack (SaaS) que criei do zero para resolver um problema real: a complexidade do gerenciamento financeiro para casais, famílias e grupos.





Status do Projeto

🚀 Ativo e em desenvolvimento

Meu Papel

👨‍💻 Arquiteto e Desenvolvedor Fullstack (Solo)

Código-Fonte

🔒 Privado / Proprietário

Nota: Este repositório serve como uma vitrine técnica e um estudo de caso detalhado do projeto Clarify. O código-fonte não é público, mas a arquitetura, as decisões técnicas e as funcionalidades estão documentadas aqui para fins de portfólio.

🎯 O Problema
Grupos de pessoas que compartilham finanças (seja uma família, um casal ou amigos dividindo um aluguel) frequentemente recorrem a planilhas confusas, anotações em bloco de notas ou simplesmente "cálculos de cabeça", gerando estresse, falta de transparência e dificuldade em atingir objetivos financeiros comuns.

✨ A Solução: Clarify
Clarify centraliza tudo em uma interface intuitiva, com uma carteira compartilhada, metas em grupo e ferramentas inteligentes, trazendo clareza e paz para a vida financeira partilhada.

🎥 Demonstração em Vídeo
(Grave um GIF ou vídeo curto (1-2 min) e coloque aqui. Mostre o fluxo principal: login, visualização do dashboard, adição de uma despesa pela IA, progresso de uma meta e o painel de colaborador. Use um serviço como o imgur ou youtube para hospedar.)

[Assista à Demonstração em Vídeo]

🏛️ Arquitetura Técnica
A aplicação foi projetada com uma arquitetura desacoplada, com uma API RESTful no backend e um frontend dinâmico e leve.

![Diagrama de Arquitetura do Clarify]
(Crie um diagrama simples usando ferramentas como draw.io ou Excalidraw e adicione a imagem aqui. Mostre o fluxo: Cliente -> Frontend -> API FastAPI -> Banco de Dados PostgreSQL, e as integrações com Mercado Pago, Gemini, etc.)

🚀 Funcionalidades Principais
Funcionalidade

Descrição Detalhada

🔐 Autenticação Segura

Sistema completo de login e registro com tokens JWT para dois tipos de perfis: Clientes e Colaboradores.

🛡️ Proteção Anti-Fraude

Implementação de Rate Limiting e bloqueio de contas para proteger contra ataques de força bruta.

📦 Modelagem de Dados

Uso de SQLAlchemy ORM para criar um banco de dados relacional complexo, com relacionamentos e tabelas de associação.

💳 Integração de Pagamentos

Ciclo completo de assinaturas com Mercado Pago, incluindo criação, gerenciamento e webhooks.

🤖 Inteligência Artificial

Análise de transações financeiras com Google Gemini usando linguagem natural.

👥 Painel Administrativo

Interface para colaboradores com diferentes níveis de permissão (ADM, Suporte) para gerenciar usuários, planos e tickets.

💧 Sanitização de Inputs

Proteção contra ataques XSS através da sanitização de todos os dados inseridos pelo usuário.

🛠️ Tecnologias Utilizadas
Categoria

Tecnologias

Backend



Frontend



Banco de Dados



APIs Externas

Mercado Pago, Google Gemini

💡 Desafios Técnicos e Soluções
Durante o desenvolvimento, enfrentei alguns desafios interessantes:

Desafio: Sistema de Permissões Flexível

Problema: Precisava de um sistema de autorização que diferenciasse não apenas clientes de colaboradores, mas também diferentes tipos de colaboradores (ex: adm vs. suporte).

Solução: Incorporei o "cargo" do colaborador diretamente no payload do token JWT. No backend, criei dependências em FastAPI que verificam esse cargo em rotas críticas, garantindo que apenas administradores pudessem, por exemplo, gerenciar planos de assinatura.

Desafio: Proteger contra Credential Stuffing

Problema: A tela de login é um alvo comum para ataques de força bruta.

Solução: Implementei um sistema de rate limiting por IP e um contador de tentativas de login falhas por conta. Após 5 tentativas sem sucesso, a conta é bloqueada temporariamente. Isso foi feito com um cache em memória e Locks para garantir a segurança em ambientes com múltiplos workers.

Desafio: Experiência do Usuário em Assinaturas Concedidas

Problema: Uma assinatura concedida por um admin não existe no Mercado Pago, o que gerava um erro 404 ao tentar gerenciá-la.

Solução: Criei uma lógica no backend que identifica essas assinaturas "administrativas" (pelo seu ID único) e retorna um campo especial (managed_by: "admin"). No frontend, usei esse campo para renderizar uma interface diferente, informando ao usuário que seu plano é uma cortesia e não pode ser gerenciado, resolvendo o erro e melhorando a UX.

Obrigado por analisar meu projeto! Ficarei feliz em discutir a arquitetura e as decisões técnicas com mais detalhes.
