# FIAP - Faculdade de Informática e Administração Paulista

<p align="center">
<a href= "https://www.fiap.com.br/"><img src="assets/logo-fiap.png" alt="FIAP - Faculdade de Informática e Admnistração Paulista" border="0" width=40% height=40%></a>
</p>

<br>

# PROJETO - <img width="50" height="50" alt="image" src="https://github.com/user-attachments/assets/0dd30789-c0b7-4310-92b9-fa4bd6091244" />  SPRINT 1 YOUVISA 

![capa](https://github.com/Mu1518/FIAP-FASE3-Sprint1_Youvisa/blob/main/assets/Capa_Sp1.png)

## Grupo 3

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

## 🔍 SOBRE O PROJETO
Bem-vindos ao Challenge do Youvisa.

A **YOUVISA**, empresa especializada na emissão de vistos e passaportes, enfrenta desafios de **produtivida** devido ao alto volume de consultas repetitivas, **atendimento fragmentado entre diferentes canais** e **dificuldade na gestão de documentos enviados por clientes**.

Para resolver esse cenário, o grupo desenvolveu o **VistoBot Multi-Channel** — uma **plataforma inteligente de atendimento e automação** que combina **chatbots multicanais**, **Processamento de Linguagem Natural (NLP)** e **Automação Robótica de Processos (RPA)**.

A solução tem como objetivos:
- **Automatizar até 80% das interações** iniciais com o cliente por meio de respostas rápidas e triagem automatizada de documentos;
- **Unificar os canais de atendimento** (Telegram, WhatsApp e Webchat), mantendo histórico e consistência nas respostas;
- **Validar documentos de forma automática**, utilizando **OCR (Reconhecimento Óptico de Caracteres)** integrado ao backend em Python;
- **Garantir segurança e rastreabilidade** dos dados com armazenamento no **Oracle APEX**, seguindo práticas da **LGPD**.


O projeto do bot com escalabilidade para multicanais propõe a redução de custos operacionais, melhora da experiência do usuário, oferece um fluxo inteligente de atendimento que decide, de forma autônoma, quando resolver a solicitação via bot ou encaminhar para o atendimento humano.

Este repositório tem como finalidade documentar e armazenar todo o trabalho desenvolvido ao longo do Sprint 1.   

## 🧩 ARQUITETURA DA SOLUÇÃO

A Sprint 1 teve como foco a definição técnica e conceitual da arquitetura do bot, que será chamado **Stuart**(ou Stu), estabelecendo a base estrutural do projeto para as próximas etapas de desenvolvimento.

O principal objetivo desta entrega foi planejar a integração entre os módulos de automação, NLP, OCR e banco de dados, garantindo que a plataforma do Stuart fosse escalável, segura e alinhada às operações da YOUVISA.

A arquitetura proposta para o Stu adota um modelo de microfluxos orquestrados em Python (FastAPI), responsável por centralizar suas decisões e conectar os principais componentes do sistema:

Chatbot Multicanal: ponto de entrada das interações do usuário via Telegram, com expansão planejada para WhatsApp e Webchat.

Módulo de NLP: realiza a classificação de intenções e a extração de entidades relevantes (país, tipo de visto, status de processo).

Pipeline OCR/RPA: executa a leitura e validação automática de documentos enviados, reduzindo o tempo de triagem.

Banco de Dados Oracle APEX: armazena informações de autenticação, registros de atendimento e logs de transbordo humano.

Camada de Segurança: utiliza tokens de acesso e criptografia de dados em trânsito e repouso.

Módulo de Transbordo Humano: direciona casos complexos para agentes, preservando o contexto completo da interação.

Essa estrutura permite que o Stuart automatize até 80% dos atendimentos, mantendo segurança, rastreabilidade e uma experiência fluida para o usuário. Com isso, a Sprint 1 consolida a fundação técnica necessária para que a YOUVISA evolua rumo a um atendimento digital inteligente, eficiente e integrado com o Stu.


## 📁 Estrutura das Pastas

- <b>assets</b>: imagens utilizadas no projeto e documentação
  
- <b>docs</b>: documentos prinicpais

- <b>README.md</b>: guia e explicação geral sobre o projeto


## 📣 PRÓXIMOS PASSOS 

Com a arquitetura definida e a documentação concluída, o próximo ciclo do projeto concentra-se na **implementação prática e validação técnica** do |Bot Stu.  

As atividades estão organizadas em quatro frentes principais:

### 🧠 1. Inteligência e Automação
- Implementar o **chatbot no Telegram** para atuar como Tier 1 de atendimento, gerenciando e resolvendo os fluxos mais básicos e consultas simples. 
- Integrar o módulo de **NLP (spaCy/NLTK)** para identificar intenções e entidades.  
- Desenvolver o pipeline de **OCR (Tesseract)** para validação automática de documentos enviados pelos usuários.

### ☁️ 2. Infraestrutura e Integração
- Conectar o backend em **Python (FastAPI)** ao **Oracle APEX** para persistência e gestão segura de dados.  
- Configurar autenticação e logs centralizados para rastrear interações e desempenho.  

### 🤝 3. Atendimento Humano
- Implementar o módulo de **transbordo inteligente**, responsável por direcionar ao agente humano não apenas os casos complexos, mas também as solicitações que exigem autenticação, o envio de documentos no fluxo híbrido, e as questões não resolvidas pelo Tier 1 (consultas simples). 
- Criar uma interface simples para registro, acompanhamento e fechamento de tickets.  

### 🔍 4. Testes e Monitoramento
- Executar testes de desempenho e precisão do NLP.  
- Monitorar métricas de uso, como tempo médio de resposta, taxa de resolução automática e volume de transbordos.  

            

##  :octocat: CONTRIBUIÇÕES AO PROJETO

Ficamos muito felizes com a sua contribuição e valorizamos cada sugestão e esforço dedicado a aprimorá-lo.

Como Contribuir: 

* Clique no botão "Fork" no canto superior direito desta página para criar uma cópia do repositório na sua conta do GitHub.

* Clone o repositório forkado para o seu ambiente de desenvolvimento local.

* Crie uma branch separada para a sua contribuição, desenvolva suas modificações e realize os commits necessários na sua branch.

* Quando suas alterações estiverem prontas, envie um Pull Request do seu fork para a branch main deste repositório.

Seu Pull Request será revisado pela equipe e, se tudo estiver correto, será aceito e suas contribuições serão integradas ao projeto 😃!


## 🗃 Histórico de lançamentos

* 1.0.0 - 03/11/2025
    

## 📋 Licença

<img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/cc.svg?ref=chooser-v1"><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/by.svg?ref=chooser-v1"><p xmlns:cc="http://creativecommons.org/ns#" xmlns:dct="http://purl.org/dc/terms/"><a property="dct:title" rel="cc:attributionURL" href="https://github.com/agodoi/template">MODELO GIT FIAP</a> por <a rel="cc:attributionURL dct:creator" property="cc:attributionName" href="https://fiap.com.br">Fiap</a> está licenciado sobre <a href="http://creativecommons.org/licenses/by/4.0/?ref=chooser-v1" target="_blank" rel="license noopener noreferrer" style="display:inline-block;">Attribution 4.0 International</a>.</p>
