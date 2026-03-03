# FIAP - Faculdade de Informática e Administração Paulista

<p align="center">
<a href= "https://www.fiap.com.br/"><img src="assets/logo-fiap.png" alt="FIAP - Faculdade de Informática e Admnistração Paulista" border="0" width=40% height=40%></a>
</p>

<br>

# ENTERPRISE CHALLENGE - SPRINT 2 YOUVISA

![capa]

## Grupo 4

## 👨‍🎓 Integrantes: 
- <a href="https://www.linkedin.com/in/jonatasgomes">Jônatas Gomes Alves</a>
- <a href="https://www.linkedin.com/in/iolanda-helena-fabbrini-manzali-de-oliveira-14ab8ab0">Iolanda Helena Fabbrini Manzali de Oliveira</a>
- <a href="https://www.linkedin.com/company/inova-fusca">Murilo Carone Nasser</a> 
- <a href="https://www.linkedin.com/in/pedro-eduardo-soares-de-sousa-439552309">Pedro Eduardo Soares de Sousa</a>
- <a href= "https://www.linkedin.com/in/amanda-fragnan-b61537255">Amanda Fragnan<a>

## 👩‍🏫 Professores:
### Tutor(a) 
- <a href="https://www.linkedin.com/in/leonardoorabona">Leonardo Ruiz Orabona</a>
### Coordenador(a)
- <a href="https://www.linkedin.com/company/inova-fusca">Andre Godoi Chaviato</a>

## 🌎SOBRE O PROJETO*
O **PROJETO SPRINT 2 YOUVISA** é uma plataforma inteligente desenvolvida para simplificar, automatizar e gerenciar processos de solicitação de vistos de estudo. É uma aplicação Single Page Application (SPA) desenvolvida em React com TypeScript, projetada para simular um assistente virtual de atendimento ao cliente. Ele integra um Chatbot inteligente ("Stu"), um pipeline de processamento de documentos via OCR (Reconhecimento Óptico de Caracteres) e um painel de gestão de tarefas. 

Diferente de sistemas tradicionais baseados em formulários estáticos, o YOUVISA emprega Agentes de IA Multimodais para ler, interpretar e validar documentos (Passaportes, Extratos, Cartas de Aceite) em tempo real, aplicando regras consulares complexas sem intervenção humana

![alt text](https://img.shields.io/badge/React-18-blue?logo=react) 
![alt text](https://img.shields.io/badge/TypeScript-5.0-blue?logo=typescript) 
![alt text](https://img.shields.io/badge/Vite-5.0-646CFF?logo=vite) 
![alt text](https://img.shields.io/badge/AI-Google%20Gemini-8E75B2?logo=google) 
![alt text](https://img.shields.io/badge/Styling-Tailwind-38B2AC?logo=tailwindcss)
![alt text](https://img.shields.io/badge/Oracle-Autonomous_DB-F80000?logo=oracle)
![alt text](https://img.shields.io/badge/Backend-PL%2FSQL-black)

---

# 🚀 **PRINCIPAIS FUNCIONALIDADES**

### 🤖 Chatbot Inteligente (Stu)
- Assistente virtual proativo que guia o usuário.
- Contexto de conversa mantido para recuperação de senhas e fluxo de decisões.
- Integração com base de dados de vistos de diversos países (`visaData.ts`).

### 👁️ Visão Computacional & IA Generativa
- **OCR Avançado:** Upload de documentos (Passaportes, RGs, Extratos).
- **Validação de Regras de Negócio:** Verifica datas de expiração, consistência de dados e legibilidade utilizando o modelo **Google Gemini 2.5 Flash**.
- **Feedback Imediato:** O usuário recebe aprovação ou rejeição do documento em segundos.

### 📊 Painel do Cliente (Dashboard)
- Barra de progresso visual do processo de visto.
- Lista de documentos pendentes vs. enviados.
- Feedback visual de status (Aprovado ✅, Rejeitado ❌, Em Análise ⚠️).

### 🛡️ Painel Administrativo
- Gestão de usuários e documentos.
- Geração de relatórios em PDF (Geral e Dossiê Individual) via `jsPDF`.
- Métricas e KPIs (Taxa de aprovação, tipos de documentos mais enviados).
- Backup do banco de dados local (JSON).

### ☁️ Arquitetura Híbrida (Offline-First)
- **LocalDB:** Persistência imediata via LocalStorage para experiência fluida.
- **Oracle ORDS:** Sincronização com banco de dados Oracle via API REST.
- **Notificações:** Envio de e-mails transacionais via EmailJS.
- **Gestão de Ciclo de Vida:** CRUD completo de usuários com exclusão em cascata (Cascade Delete).

---

## **🛠️ TECNOLOGIAS UTILIZADAS**

 **Frontend:**
- [React](https://react.dev/) + [Vite](https://vitejs.dev/)
- [TypeScript](https://www.typescriptlang.org/)
- [Tailwind CSS](https://tailwindcss.com/) (Estilização)
- [Lucide React](https://lucide.dev/) (Ícones)

**Inteligência Artificial:**
- [Google Generative AI SDK](https://www.npmjs.com/package/@google/genai) (Modelo Gemini 2.5 Flash)

**Backend & Serviços:**
- **Oracle Database** (via ORDS REST APIs)
- **EmailJS** (Automação de e-mails)
- **Local Storage** (Persistência local)

**Utilitários:**
- `jspdf` & `jspdf-autotable` (Relatórios)

---

## **⚙️ PIPELINE DA SOLUÇÃO**

O fluxo de dados da aplicação segue uma abordagem centrada no cliente com validação assistida por IA:

1.  **Entrada:** O usuário interage via Chat ou Dashboard e faz upload de uma imagem.
2.  **Pré-processamento:** A imagem é convertida para Base64 no navegador.
3.  **Análise (IA):** O payload é enviado para o **Google Gemini** com um prompt de sistema robusto (OCR + Regras de Visto).
4.  **Processamento:** O JSON retornado pela IA é interpretado (Válido/Inválido, Dados extraídos).
5.  **Persistência:** 
    *   Salva instantaneamente no `LocalDB` (Browser).
    *   Tenta sincronização com a API Oracle (`/ords/fiap/youvisa`).
6.  **Notificação:** Dispara e-mail de status via **EmailJS**.

---

## **ESTRUTURA DO PROJETO**

A estrutura do projeto está organizada para separar a lógica de interface (React), a lógica de negócios (Services) e os artefatos de referência do Banco de Dados Oracle (DB).

![estrutura](https://github.com/Ioiofmanzali/Ioiofmanzali-FIAP_FASE4_Sprint2_Youvisa/blob/main/assets/estrutura.JPG)

---

## **🧩 FLUXOGRAMA DETALHADO DA ARQUITETURA**

![fluxoyv](https://github.com/Ioiofmanzali/Ioiofmanzali-FIAP_FASE4_Sprint2_Youvisa/blob/main/assets/fluxo_yv.jpg)

- O fluxograma tambem pode ser acessado através do link: [Fluxo](https://drive.google.com/file/d/1blecTDD8D_ZqJx5y8haf94RYTqLbpMt2/view?usp=sharing)
  
---

## **COMO EXECUTAR O PROJETO**

**Pré-requisitos**
- Node.js (v18 ou superior)
- NPM ou Yarn
- Chave de API do Google Gemini (Gratuita no Google AI Studio e EmailJS)

**Passo 1: Clonar ou Baixar**

Baixe os arquivos do projeto para uma pasta local e os **posicione conforme descrito no tópico "Estrutura de Pastas"**.

Se preferir tambem disponibilizamos os arquivos de código do projeto através do link abaixo, com exceção do arquivo .env:
- [Projeto Youvisa SP2](https://drive.google.com/drive/folders/1oICDvExqfiOz8XHSuX-EdkJt8v8R_14-?usp=drive_link)

**Passo 2: Instalar Dependências**

Abra o terminal na pasta do projeto, digite o comando para entrar na pasta onde salvou seu projeto (cd C:/Users/seu_usuario/pasta_do_projeto) e execute o comando **npm install**

![estutura](https://github.com/Ioiofmanzali/Ioiofmanzali-FIAP_FASE4_Sprint2_Youvisa/blob/main/assets/etapa1.jpg) 

![estutura](https://github.com/Ioiofmanzali/Ioiofmanzali-FIAP_FASE4_Sprint2_Youvisa/blob/main/assets/etapa2.jpg) 

Obs: Para que o comando rodasse com sucesso no terminal da máquina de teste utilizada foi necessário acrescentar .cmd imediatamente apos o npm. Plataformas diferentes (Mac, Windows) podem exigir ajustes nos comandos a serem digitados.       
 
**Passo 3: Configurar as Variáveis de Ambiente**

O sistema precisa de uma chave da Google para funcionar. 

Através de uma conta Google:
 * obtenha sua chave gratuita da API no Google AI Studio
 * crie sua chave pública e templates no site do EmailJS (conta gratuita, limita a quantidade de templates permitidos e interações).

Obs: para esse projeto foi criada um email dedicado para o projeto.

Crie um arquivo chamado .env na raiz do projeto e adicione as seguintes linhas de código: 
       
       API_KEY=Sua_Chave_Comeca_Com_AIza_Aqui
       
       VITE_API_KEY=sua_chave_gemini
       
       VITE_EMAILJS_SERVICE_ID=service_id
       
       VITE_EMAILJS_PUBLIC_KEY=public_key
       
       VITE_TEMPLATE_DOC_STATUS=template_id
       
       VITE_TEMPLATE_PROCESS_STATUS=template_id
       
       VITE_EMAIL_SENDER=email@escolhido.com

       
**Passo 4: Rodar o Projeto**

Execute o servidor de desenvolvimento:

![estutura](https://github.com/Ioiofmanzali/Ioiofmanzali-FIAP_FASE4_Sprint2_Youvisa/blob/main/assets/etapa3.jpg) 

![estutura](https://github.com/Ioiofmanzali/Ioiofmanzali-FIAP_FASE4_Sprint2_Youvisa/blob/main/assets/etapa4.jpf.JPG) 

PS: O terminal mostrará um link. Abra-o no seu navegador.

![estutura](https://github.com/Ioiofmanzali/Ioiofmanzali-FIAP_FASE4_Sprint2_Youvisa/blob/main/assets/capa.jpg)

### **Deploy e Build** (opcional)

Para gerar os arquivos finais para produção (hospedagem no Vercel, Netlify, etc.):

        npm run build

PS: Isso criará uma pasta dist/ otimizada e minificada.

---

## :octocat: CONTRIBUIÇÕES AO PROJETO

Ficamos muito felizes com a sua contribuição e valorizamos cada sugestão e esforço dedicado a aprimorá-lo.

Como Contribuir: 

* Clique no botão "Fork" no canto superior direito desta página para criar uma cópia do repositório na sua conta do GitHub.

* Clone o repositório forkado para o seu ambiente de desenvolvimento local.

* Crie uma branch separada para a sua contribuição, desenvolva suas modificações e realize os commits necessários na sua branch.

* Quando suas alterações estiverem prontas, envie um Pull Request do seu fork para a branch main deste repositório.

Seu Pull Request será revisado pela equipe e, se tudo estiver correto, será aceito e suas contribuições serão integradas ao projeto 😃!

---

## 📁 ESTRUTURA DE PASTAS

- <b>assets</b>: imagens utilizadas no projeto

- <b>youvisa_project</b>: arquivos principais do projeto divididos em pastas e subpastas de acordo com a estrutura do projeto 

- <b>docs<b>: arquivo paises.json

- <b>relatorio<b>: dOcumentação técnica em pdf e relatorios gerenciais gerados pela aplicação  
  
- <b>README.md</b>: guia e explicação geral sobre o projeto

---

## **PRÓXIMOS PASSOS E DESAFIOS**

Como o projeto opera atualmente em um modelo *client-side* com simulação de persistência (`localStorage`), os próximos passos visam a profissionalização da arquitetura, implementação real do backend e endurecimento da segurança.

### 🚧 1. Backend e Integração (Prioridade Alta)
Atualmente, a aplicação simula o backend. O objetivo é conectar com a infraestrutura Oracle definida na pasta `/src/db`.
*   **Implementação da API:** Colocar os serviços REST definidos em `rest_api.sql` em produção no Oracle Cloud (ORDS).
*   **Middleware de Segurança (BFF):** Criar um servidor intermediário em Python para atuar como *Backend for Frontend*.
    *   *Motivo:* Hoje, a chave da API do Google Gemini (`API_KEY`) e as credenciais do EmailJS estão expostas no Frontend. O backend deve intermediar essas chamadas para ocultar as chaves.
*   **Sincronização Real:** Substituir a lógica de "tentativa de upload" do `apiService.ts` por uma fila de sincronização robusta que gerencie falhas de rede e retentativas automáticas.

### 🔐 2. Segurança e Criptografia
Como lidamos com **PII (Personal Identifiable Information)** — Passaportes, RGs e dados financeiros — a segurança é o pilar mais crítico.
*   **Criptografia em Trânsito:** Garantir que todas as comunicações (Front ↔ Back ↔ Oracle) ocorram estritamente via **HTTPS/TLS 1.3**.
*   **Criptografia em Repouso:**
    *   Implementar criptografia no banco de dados Oracle (TDE - Transparent Data Encryption) para as colunas sensíveis.
    *   **Não armazenar senhas em texto plano.** Migrar a lógica de login atual para uso de **BCrypt** ou **Argon2** no backend.
*   **Proteção do LocalStorage:**
    *   *Desafio:* O `localStorage` é vulnerável a ataques XSS.
    *   *Solução:* Migrar tokens de sessão para **HttpOnly Cookies** e, se necessário persistir dados sensíveis offline, utilizar **IndexedDB** com criptografia antes de salvar.
*   **Sanitização:** Implementar validação rigorosa no backend (Zod/Joi) para prevenir SQL Injection nos endpoints do Oracle.

### ⚖️ 4. Desafios de Conformidade (LGPD/GDPR)
*   **Retenção de Dados:** Implementar rotinas automáticas no banco de dados para excluir imagens de documentos após o processamento e validação, mantendo apenas os metadados necessários, para reduzir o risco de vazamento.
*   **Termos de Uso:** Adicionar checkbox obrigatório de consentimento para processamento de dados biométricos/pessoais via IA antes do upload.

### 🧠 5. Melhorias na IA
*   **Fallback de Modelo:** Implementar lógica para usar modelos menores/mais baratos se o Gemini falhar ou demorar.
*   **Detecção de Fraude:** Treinar ou configurar o prompt para detectar indícios de manipulação digital na imagem.

---

## **VIDEO DEMONSTRATIVO**

Assista ao vídeo e explore a experiência do usuário com o Stu.

[Clique para Assistir](https://youtu.be/f8mrI1JxSdE)

---

## 🗃 HISTÓRICO DE LANÇAMENTOS

![Versão 1.0.0](https://img.shields.io/badge/Vers%C3%A3o%201.0.0-darkblue?style=flat)  - 22/11/2025
    
## 📋 Licença

<img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/cc.svg?ref=chooser-v1"><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/by.svg?ref=chooser-v1"><p xmlns:cc="http://creativecommons.org/ns#" xmlns:dct="http://purl.org/dc/terms/"><a property="dct:title" rel="cc:attributionURL" href="https://github.com/agodoi/template">MODELO GIT FIAP</a> por <a rel="cc:attributionURL dct:creator" property="cc:attributionName" href="https://fiap.com.br">Fiap</a> está licenciado sobre <a href="http://creativecommons.org/licenses/by/4.0/?ref=chooser-v1" target="_blank" rel="license noopener noreferrer" style="display:inline-block;">Attribution 4.0 International</a>.</p>
