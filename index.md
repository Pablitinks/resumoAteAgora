# 🛜Redes, 📶Internet e 🤖Versionamento

Este documento consolida os principais conceitos abordados sobre a infraestrutura da internet, desenvolvimento web e as práticas de controle de versão com Git e GitHub.

<img src="https://i.pinimg.com/originals/d0/23/83/d02383145fefa4a07d31a390e3674817.png" width="300" /> <img src="https://images.tcdn.com.br/img/img_prod/1354873/180_rede_de_descanso_casal_peroba_235_variacao_259_1_0cb23fb04bca1375390144816402be6a.png" width="300" />

## 1. Redes, Internet e Desenvolvimento Web

### 1.1. Fundamentos de Redes e Internet

-   Funcionamento de um roteador e a operação do NAT.
-   Uso do Linux como roteador e o conceito de switch.
-   Criação de redes internas (sub-redes / VLANs).
-   Endereçamento IP: Fixo vs. Dinâmico, IPv4 vs. IPv6.
-   CGNAT (Carrier-Grade NAT) e o bloqueio de portas (80, 443).
-   Máscara de rede e operações bitwise.
-   Proxy, VPN e Throttling (controle de desempenho).
-   Abstração tecnológica e o conceito de instância agnóstica.

### 1.2. APIs e Desenvolvimento Web

-   API e Web Services.
-   Arquitetura REST e Microserviços.
-   Desacoplamento e controle de estado (Conceito de Web 2.0).
-   Navegadores Web e a estrutura de um site.
-   Introdução a Linguagens de Marcação (HTML).
-   Estrutura básica de um documento HTML.
-   Diferença entre Elementos, Tags, Atributos e Valores.
-   Classificação de Elementos (Texto, Formulário, Mídia).
-   Uso de Classes e IDs.
-   Criação de Listas, Tabelas e Formulários.

### 1.3. Ferramentas e Produtividade

-   **VS Code:**  Atalhos essenciais e extensões para produtividade.
-   **Emmet:**  Uso de abreviações para acelerar a escrita de HTML/CSS.
-   Preparação do ambiente de trabalho (arquivos  `.html`  e diretórios).
  
<img src="https://stickerly.pstatic.net/sticker_pack/XWck3Qe1XlxSv8NSW31w/L11DTE/16/c186991d-1ced-438d-9004-bb40c95e53aa.png" width="300" /> <img src="https://miro.medium.com/1*dDNpLKu_oTLzStsDTnkJ-g.png" width="600" />

## 2. Controle de Versão com Git e GitHub

### 2.1. Fundamentos do Git

-   **O que é Git?**  Sistema de controle de versão distribuído. Alternativas incluem SVN, CSV e TeamFS.
-   **Diagrama de Git:**
    -   **Working Tree:**  O diretório atual de trabalho.
    -   **Index (Stage):**  Área intermediária onde as alterações são preparadas para o commit.
    -   **Commits:**  "Fotografias" salvas do estado do projeto.
-   **Conceitos Essenciais:**
    -   **Commit:**  Um snapshot do repositório, identificado por um hash  **SHA1**.
    -   **Branch:**  Um ponteiro móvel para um commit.  `master`/`main`  é a branch principal.
    -   **HEAD:**  Ponteiro que indica onde você está no momento (geralmente aponta para a branch atual).
    -   **Tag:**  Um marcador fixo para um commit específico (ex:  `v1.0`).

### 2.2. Comandos e Operações Locais

-   **Iniciando e Gerenciando:**
    -   `git init`: Inicia um novo repositório.
    -   `git status`: Verifica o estado das alterações.
    -   `git commit`: Salva as alterações do Index no repositório.
    -   `git commit --amend`: Modifica o último commit.
-   **Gerenciando Alterações:**
    -   `git restore`: Descarta alterações em arquivos.
    -   `git stash`: Salva temporariamente alterações não commitadas.
    -   `git stash pop`  /  `apply`: Restaura as alterações salvas.
-   **Ignorando Arquivos:**
    -   `.gitignore`: Arquivo que especifica quais arquivos e pastas devem ser ignorados pelo Git (essencial para arquivos como  `.env`).

### 2.3. Branches e Merges

-   **Trabalhando com Branches:**
    -   `git branch <nome>`: Cria uma nova branch.
    -   `git checkout <nome>`: Muda para a branch especificada.
-   **Tipos de Merge:**
    -   **Fast-forward:**  Ocorre quando a branch de destino não tem novos commits desde que a outra branch foi criada. O ponteiro simplesmente avança.
    -   **Three-way merge:**  Cria um novo "commit de merge" que une o histórico de duas branches que divergiram.
-   **Conflitos de Merge:**
    -   Ocorrem quando as mesmas linhas são alteradas em ambas as branches.
    -   O Git insere marcadores no código para que a resolução seja feita manualmente.

### 2.4. Colaboração com Repositórios Remotos (GitHub)

-   **Sincronização:**
    -   `git push`: Envia commits locais para o repositório remoto.
    -   `git fetch`: Baixa as alterações do remoto, mas não as integra.
    -   `git pull`: Baixa e integra as alterações (`fetch`  +  `merge`).
-   **Pull Request (PR):**
    -   **Fluxo:**  Propor a integração de uma branch em outra para revisão.
    -   **Interações:**  `Comment`  (comentar),  `Approve`  (aprovar),  `Request Changes`  (pedir alterações).
-   **Comparando Mudanças:**
    -   Pela aba "Files changed" no GitHub.
    -   `git diff A..B`: Diferença entre os estados finais de A e B.
    -   `git diff A...B`: Mudanças em B desde o ancestral comum com A.
-   **Resolução de Conflitos (PR):**
    -   **Local (Recomendado):**  `git pull`  na  `main`,  `git merge main`  na sua branch, resolver e  `git push`.
    -   **Remoto:**  Usando a ferramenta de resolução do GitHub.

### 2.5. Boas Práticas e Fluxos de Trabalho

-   **Fluxo de Colaboração:**  Clonar o repositório, criar uma branch para a tarefa, fazer commits frequentes, enviar a branch e abrir um Pull Request.
-   **Regras:**  Evitar commits diretos na  `main`, manter a  `main`  sempre estável e apagar branches após o merge.
-   **Estratégias:**  Git Flow, Feature Branches.
-   **Ambiente:**  Uso do WSL (Windows Subsystem for Linux) para um ambiente de desenvolvimento consistente.
