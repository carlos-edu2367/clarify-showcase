Estudo de Caso: Clarify - SaaS de Gestão Financeira Colaborativa
![WhatsApp Image 2025-07-29 at 11 10 30](https://github.com/user-attachments/assets/135f25c3-5cd1-499f-8a23-f8f0292f5a52)


Clarify é uma aplicação web fullstack (SaaS) que criei do zero para resolver um problema real: a complexidade do gerenciamento financeiro para casais, famílias e grupos.

Status do Projeto: Ativo e em desenvolvimento.
Meu Papel: Arquiteto e Desenvolvedor Fullstack (Solo).
Código-Fonte: Privado / Proprietário.

Nota: Este repositório serve como uma vitrine técnica e um estudo de caso detalhado do projeto Clarify. O código-fonte não é público, mas a arquitetura, as decisões técnicas e as funcionalidades estão documentadas aqui para fins de portfólio.

🎯 O Problema
Grupos de pessoas que compartilham finanças (seja uma família, um casal ou amigos dividindo um aluguel) frequentemente recorrem a planilhas confusas, anotações em bloco de notas ou simplesmente "cálculos de cabeça", gerando estresse, falta de transparência e dificuldade em atingir objetivos financeiros comuns.

✨ A Solução: Clarify
Clarify centraliza tudo em uma interface intuitiva, com uma carteira compartilhada, metas em grupo e ferramentas inteligentes, trazendo clareza e paz para a vida financeira partilhada.

🎥 Demonstração em Vídeo
(Grave um GIF ou vídeo curto (1-2 min) e coloque aqui. Mostre o fluxo principal: login, visualização do dashboard, adição de uma despesa pela IA, progresso de uma meta e o painel de colaborador. Use um serviço como o imgur ou youtube para hospedar.)

[Link para o Vídeo de Demonstração]

🏛️ Arquitetura Técnica
A aplicação foi projetada com uma arquitetura de microsserviços desacoplada, com uma API RESTful no backend e um frontend dinâmico e leve.

![Diagrama de Arquitetura do Clarify]
(Crie um diagrama simples usando ferramentas como draw.io ou Excalidraw e adicione a imagem aqui. Mostre o fluxo: Cliente -> Frontend -> API FastAPI -> Banco de Dados PostgreSQL, e as integrações com Mercado Pago, Gemini, etc.)

Backend (Python / FastAPI)
O coração da aplicação é uma API RESTful construída com FastAPI, escolhido pela sua alta performance, documentação automática e tipagem de dados com Pydantic.

Banco de Dados: Utilizei PostgreSQL com SQLAlchemy ORM para uma modelagem de dados robusta e segura.

Segurança: A segurança foi uma prioridade máxima. Implementei:

Autenticação com tokens JWT com escopos para diferentes perfis (clientes e colaboradores).

Rate limiting e bloqueio de contas para prevenir ataques de força bruta.

Hashing de senhas (bcrypt) e sanitização de inputs para prevenir XSS.

Integrações:

Mercado Pago: Para o sistema de assinaturas, gerenciando o ciclo de vida completo do pagamento via API.

Google Gemini: Para a funcionalidade de "Registro por IA", onde o usuário descreve uma transação em linguagem natural.

Frontend (JavaScript Puro)
Optei por construir o frontend com JavaScript puro, HTML5 e TailwindCSS para criar uma experiência rápida e leve, sem a sobrecarga de frameworks. Isso também me permitiu demonstrar um domínio profundo da manipulação do DOM e da lógica de frontend.

Reatividade: A interface é renderizada dinamicamente com base nos dados recebidos da API, criando uma experiência de usuário fluida.

Dois Painéis Distintos: Desenvolvi duas interfaces separadas: uma para os clientes e outra para os colaboradores, cada uma com sua própria lógica de autenticação e funcionalidades.

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
