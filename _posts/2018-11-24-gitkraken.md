---
title: "Gitkraken - Principais Funções"
date: 2018-11-24
tags: [dev-u, git, github, gitkraken]
author: Hugo Borges
header:
    image: "/images/devu_banner.jpg"
excerpt: Dev-U, Git, Github, Gitkraken" 
---

Aqui mostrarei os principais comandos e funções do **Git** através do **Gitkraken**. Focarei em como resolver problemas específicos que costumamos encontrar quando trabalhando com a **Unity** em conjunto com o **Git**.
{: .text-justify}

Material auxiliar da própria Dev-U sobre Git: [**link**](https://drive.google.com/open?id=17EWH_fP3Ke4JDRstbJqLpBxFM-AaFR8k8B2GsCJ4_1I)
{: .text-justify}


## **Links Rápidos**
* <A href="#criando-um-repositorio">Criando um Repositório</A>
    * <A href="#principais-branches">Principais Branches</A>
    * <A href="#definindo-regras-nas-branches">Definindo regras nas Branches</A>
    * <A href="#convidando-usuários-para-o-repositório">Convidando usuários para o Repositório</A>

* <A href="#clonando-um-projeto">Clonando um Projeto</A>
* <A href="#abrindo-um-projeto-já-clonado">Abrindo um Projeto já clonado</A>
* <A href="#criando-uma-nova-branch">Criando uma nova Branch</A>
    * <A href="#boas-práticas-e-padrões">Boas Práticas e Padrões</A>

* <A href="#enviando-commits">Enviando Commits</A>
    * <A href="#boas-práticas-e-padrões">Boas Práticas e Padrões</A>
    * <A href="#amend---alterando-seu-último-commit">Amend - Alterando seu último commit </A>
    * <A href="#rebase---alterando-commits-antigos">Rebase - Alterando Commits Antigos</A>
    
* <A href="#criando-pull-requests">Criando Pull-Requests</A>
    * <A href="#boas-práticas-e-padrões">Boas Práticas e Padrões</A>
    * <A href="#tratando-conflitos">Tratando Conflitos</A>

* <A href="#testando-pull-requests">Testando Pull-Requests</A>
    * <A href="#avaliando-e-aceitando-pull-requests">Avaliando e Aceitando Pull-Requests</A>
    * <A href="#sugerindo-alterações">Sugerindo Alterações</A>

* <A href="#situações-menos-comuns">Situações menos comuns</A>
    * <A href="#descartando-commits-já-feitos">Descartando commits já feitos</A>
    * <A href="#buscando-alterações-no-remoto-sem-perder-seu-trabalho-atual">Buscando alterações no remoto sem perder seu trabalho atual</A>
    * <A href="#rebase---trazendo-alterações-na-develop-para-sua-branch">Rebase - Trazendo alterações na Develop para sua branch</A>


# Criando um Repositório

Para criar um repositório, primeiro entre no [**GitHub**](https://www.github.com) com sua conta.
{: .text-justify}

<img src="{{ site.url }}{{ site.baseurl }}/images/gitkraken/github_login_page.JPG" alt="Github Login Page">{: .center-image }

Após entrar com sua conta, na tela inicial serão exibidos todos os seus repositórios. Junto a eles, um botão para criar um novo repositório.
{: .text-justify}

<img src="{{ site.url }}{{ site.baseurl }}/images/gitkraken/github_first_page.JPG" alt="Github First Page">{: .center-image }

A tela para criação de um novo repositório será como a seguinte:
{: .text-justify}

<img src="{{ site.url }}{{ site.baseurl }}/images/gitkraken/github_new_repository.JPG" alt="Github New Repository">{: .center-image }

* <A href="#links-rápidos">Voltar ao Início</A>

## Principais Branches

Em nossos projetos, costumamos seguir algumas convenções de nomes para as *Branches*, de modo a manter a organização e para todos os membros consigam interagir em todos repositórios.
{: .text-justify}

Geralmente, um projeto inicia-se com **3 Branches**:
{: .text-justify}
1. Develop
2. Pre-Release
3. Release

Logo após a criação do repositório, só existirá a *branch* **Master**, sendo possível criar novas *branches* pelo menu onde é exibido os nomes das *branches*
{: .text-justify}

<img src="{{ site.url }}{{ site.baseurl }}/images/gitkraken/github_repository_page.JPG" alt="Github Repository Page">{: .center-image }


<img src="{{ site.url }}{{ site.baseurl }}/images/gitkraken/github_create_branch.JPG" alt="Github Create Branch">{: .center-image }


<img src="{{ site.url }}{{ site.baseurl }}/images/gitkraken/github_branches_created.JPG" alt="Github Branches Created">{: .center-image }


Após criadas as *branches*, como mostrado na imagem acima, é necessário setar a *branch* **Develop** como a nossa nova *branch* principal de desenvolvimento, e também é necessário deletar a *branch* **Master**.
{: .text-justify}


Primeiro, para setar a branch **Develop** como a nova padrão, entre nas Configurações do repositório, em **Settings**, e depois no menu lateral **Branches**. Na tela que aparecerá será possível alterar a *branch* principal do repositório.
{: .text-justify}

<img src="{{ site.url }}{{ site.baseurl }}/images/gitkraken/github_default_branch.JPG" alt="Github Default Branch">{: .center-image }

Para deletar a branch **Master**, basta entrar em **Code/branches** e deletar a branch **Master**.
{: .text-justify}

<img src="{{ site.url }}{{ site.baseurl }}/images/gitkraken/github_delete_master.JPG" alt="Github Delete Master">{: .center-image }

* <A href="#links-rápidos">Voltar ao Início</A>

## Definindo regras nas Branches

Caso o projeto em que deseja trabalhar tenha mais de 1 contribuidor, é interessante impedir que os seus usuários enviem *commits* diretamente para as **3 branches** principais, precisando passarem pela avaliação de um *Pull-Request*. Para isso, é necessário configurar algumas regras para as *branches*.
{: .text-justify}

Novamente no menu **Settings/Branches**, desta vez utilizaremos a opção **Add Rule**.
{: .text-justify}

<img src="{{ site.url }}{{ site.baseurl }}/images/gitkraken/github_add_rule.JPG" alt="Github Add Rule">{: .center-image }

 No caso, colocaremos a regra de que será necessário pelo menos 1 *review* através do Pull-Request para que o código seja aprovado para a *Branch*. Faça o procedimento abaixo para as branches **Develop**, **Pre-Release** e **Release**.
{: .text-justify}

<img src="{{ site.url }}{{ site.baseurl }}/images/gitkraken/github_add_rule_2.JPG" alt="Github Add Rule2">{: .center-image }

* <A href="#links-rápidos">Voltar ao Início</A>

## Convidando usuários para o Repositório

Para adicionar um usuário do *GitHub* como colaborador, você deverá entrar no menu **Settings/Collaborators**. Então é só pesquisar pelo usuário.
{: .text-justify}

<img src="{{ site.url }}{{ site.baseurl }}/images/gitkraken/github_add_collaborator.JPG" alt="Github Add Collaborator">{: .center-image }

Após adicionado, o usuário cadastrado receberá uma notificação de convite para contribuir ao repositório. Caso deseje, o link de convite gerado por ser copiado na mesma tela, para que seja enviado manualmente para o usuário.
{: .text-justify}

<img src="{{ site.url }}{{ site.baseurl }}/images/gitkraken/github_add_collaborator_link.JPG" alt="Github Add Collaborator Link">{: .center-image }


* <A href="#links-rápidos">Voltar ao Início</A>

# Clonando um Projeto

Para clonar um projeto pelo *Gitkraken*, você deve seguir as seguintes opções:
{: .text-justify}

<img src="{{ site.url }}{{ site.baseurl }}/images/gitkraken/gitkraken_clone.JPG" alt="GitKraken Clone">{: .center-image }

O mesmo pode ser obtido pelo comando: 
{: .text-justify}

```bash
git clone https://github.com/dev-u/emburradinho_prototipo.git
```


* <A href="#links-rápidos">Voltar ao Início</A>

# Abrindo um Projeto já clonado

Para abrir um projeto já clonado pelo *GitKraken*,
{: .text-justify}

<img src="{{ site.url }}{{ site.baseurl }}/images/gitkraken/gitkraken_open.JPG" alt="GitKraken Open">{: .center-image }

* <A href="#links-rápidos">Voltar ao Início</A>

# Criando uma nova Branch

Pelo GitKraken:
{: .text-justify}

<img src="{{ site.url }}{{ site.baseurl }}/images/gitkraken/gitkraken_branch.JPG" alt="GitKraken Branch">{: .center-image }

Pela linha de comando 
{: .text-justify}

```bash
git checkout -b nome_da_branch
```


* <A href="#links-rápidos">Voltar ao Início</A>

## Boas Práticas e Padrões

O primeiro ponto a levar em consideração quando se fala de padrões é a nomenclatura.
O padrão incorporado pela *Dev-U* é o padrão usando em empresas.
{: .text-justify}

* **feature/nome_da_feature** --> Nome de *branches* para novas *features* desenvolvidas;
* **imp/nome_da_melhoria** --> IMP vem de *improvement*, onde essa *branch* seria focado na melhoria de alguma *feature* existente;
* **fix/nome_do_fix** --> *Branches* dedicadas à correção de *BUGs*;

Outro ponto{: .text-justify}
 importante, fugindo de padrões e indo mais para o que é certo, é **de onde** uma branch deve ser criada.

Resumidamente, todas as novas *branches* deverão ser criadas a partir da *branch* **DEVELOP**.
{: .text-justify}


* <A href="#links-rápidos">Voltar ao Início</A>

# Enviando Commits

Quando algum arquivo for criado\removido ou modificado na pasta do projeto, o *Gitkraken* manterá uma notificação de arquivos modificados.
{: .text-justify}

<img src="{{ site.url }}{{ site.baseurl }}/images/gitkraken/gitkraken_changes.JPG" alt="GitKraken Changes">{: .center-image }

Ao clicar em *View Changes*, será aberto um menu para seleção do quais itens deverão ir de **Unstaged** para **Staged**:
{: .text-justify}

<img src="{{ site.url }}{{ site.baseurl }}/images/gitkraken/gitkraken_staged.JPG" alt="GitKraken Staged">{: .center-image }

* No menu lateral de *Commit*, em **Unstaged** são listados os arquivos que foram modificados, desde o último *Commit*;
* Em **Staged** serão colocados os arquivos que entrarão no próximo *Commit*.
{: .text-justify}

É importante tomar cuidado para que apenas os arquivos que realmente farão parte do *commit* entrem no *commit*. Não só os arquivos, mas também devem entrar no próximo *commit* **SOMENTE** as linhas que **fazendo sentido** entrar no Commit.
{: .text-justify}

A tela de *commit* com a visualização das linhas pode ser visto na imagem abaixo.
{: .text-justify}

### Como fazer o mesmo procedimento pela linha de comando

Para visualizar quais arquivos foram modificados desde o último *commit*, poderá ser utilizada a ferramenta **TIG**:
{: .text-justify}

```bash
tig
```

<img src="{{ site.url }}{{ site.baseurl }}/images/gitkraken/bash_tig.JPG" alt="Bash TIG">{: .center-image }

Caso existam dúvidas sobre como se movimentar no ambiente *VIM* utilizado pelo **TIG**, siga [**este link.**](http://blog.locaweb.com.br/geral/tig-client-para-git-no-terminal/)
{: .text-justify}

<img src="{{ site.url }}{{ site.baseurl }}/images/gitkraken/gitkraken_branch.JPG" alt="GitKraken Branch">{: .center-image }


Vistas as alterações, pela própria ferramenta **TIG** é possível selecionar e adicionar linhas e\ou arquivos de **UNSTAGED** para **STAGED** para o próximo *commit*.
{: .text-justify}

Uma outra maneira mais simples de visualizar os arquivos modificados desde o último commit é pelo commando **git status**: 
{: .text-justify}

```bash
git status
```

Uma maneira mais fácil de adicionar arquivos separadamente é pelo commando **git add**:
{: .text-justify}

```bash
git add caminho/do/arquivo/nomedoarquivo.formato
```

Para enviar o commit:
{: .text-justify}

```bash
git commit -m "NomeDoCommit"
```

Um exemplo prático de fluxo de um commit pela linha de comando:
{: .text-justify}

<img src="{{ site.url }}{{ site.baseurl }}/images/gitkraken/bash_commit.JPG" alt="Bash Commit">{: .center-image }

* <A href="#links-rápidos">Voltar ao Início</A>

## Boas Práticas e Padrões

Para os commits, costumamos colocar uma **TAG** padrão no início da mensagem de *commit*, estamos utilizando os seguintes padrões:
{: .text-justify}

* **\[ADD\] -** Para commits que estão adicionando arquivos e\ou funcionalidades;
* **\[RMV\] -** Para commits que estão **apenas** removendo arquivos e\ou funcionalidades; 
* **\[IMP\] -** Para commits que estão implementando melhorias em uma funcionalidade já existente;
* **\[REF\] -** Para commits que estão **apenas** refatorando códigos existentes, isto é, renomeando ou movendo arquivos\códigos;
* **\[WIP\] -** Para commits que ainda estão em desenvolvimento, ou seja, estão incompletos.

Exemplos de commits:
{: .text-justify}

* **\[ADD\]** Adicionada uma nova cena;
* **\[ADD\]** Adicionada a funcionalidade do player pular;
* **\[RMV\]** Removidas algumas variáveis que não estavam sendo utilizadas;
* **\[IMP\]** Otimizado o script que checava a colisão entre o player e os inimigos;
* **\[IMP\]** Foi diminuído o número de variáveis responsáveis pelo tratamento de erros no sistema de importação de arquivos;
* **\[REF\]** Script de movimentação do player foi movido para um novo arquivo dedicado a isso;
* **\[WIP\]** Avanço na implementação do sistema procedural de plataformas. 

* <A href="#links-rápidos">Voltar ao Início</A>

## Amend - Alterando seu último commit 

Em poucas palavras, *amend* é uma forma de alterar o último *commit* realizado em uma branch de um repositório.
{: .text-justify}

**Situação hipotética:**
* Você, usuário, acabou de *commitar* uma alteração trabalhando no script de gerenciamento de plataformas;
* Após algum tempo de reflexão, você percebe que faltou a adição de uma linha de código para o *commit* em questão;
* No lugar de criar um novo *commit* para incluir a adição da nova linha, você pode alterá-lo adicionando a nova linha e, até mesmo, alterando a mensagem de *commit*.

**Como criar um ammend:**

Pelo Gitkraken: 

Pela linha de comando: 



Duas observações sobre **amend**:
1. Caso **NÃO** tenha sido dado *PUSH* no commit, o **amend** não trará nenhuma consequência negativa;
2. Caso **JÁ** tenha sido dado *PUSH* no commit, o **amend** fará com que seja necessário forçar uma reconstrução dos commits remotos.
    * **Por que isso é um problema?** Porque, caso tenha mais alguém trabalhando na mesma *branch* em que o **amend** foi realizado, caso essa pessoa já tenha dado um **Pull** e baixado para sua branch local as alterações que você está modificando, será necessário que essa pessoa reconstrua os commits locais dela.

* <A href="#links-rápidos">Voltar ao Início</A>

## Rebase - Alterando Commits antigos

* <A href="#links-rápidos">Voltar ao Início</A>

# Criando Pull-Requests

* <A href="#links-rápidos">Voltar ao Início</A>

## Boas Práticas e Padrões

* <A href="#links-rápidos">Voltar ao Início</A>

## Tratando Conflitos

* <A href="#links-rápidos">Voltar ao Início</A>

# Testando Pull-Requests

* <A href="#links-rápidos">Voltar ao Início</A>

## Avaliando e Aceitando Pull-Requests

* <A href="#links-rápidos">Voltar ao Início</A>

## Sugerindo Alterações

* <A href="#links-rápidos">Voltar ao Início</A>

# Situações menos comuns

* <A href="#links-rápidos">Voltar ao Início</A>

## Descartando commits já feitos

* <A href="#links-rápidos">Voltar ao Início</A>

## Buscando alterações no remoto sem perder seu trabalho atual

* <A href="#links-rápidos">Voltar ao Início</A>

## Rebase - Trazendo alterações na Develop para sua branch

* <A href="#links-rápidos">Voltar ao Início</A>