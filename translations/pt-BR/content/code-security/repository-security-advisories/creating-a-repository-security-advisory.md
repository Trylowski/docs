---
title: Criando uma consultoria de segurança do repositório
intro: Você pode criar um projeto de consultoria de segurança para discutir e corrigir de forma privada uma vulnerabilidade de segurança no seu projeto de código aberto.
redirect_from:
- /articles/creating-a-maintainer-security-advisory
- /github/managing-security-vulnerabilities/creating-a-maintainer-security-advisory
- /github/managing-security-vulnerabilities/creating-a-security-advisory
- /code-security/security-advisories/creating-a-security-advisory
versions:
  fpt: '*'
  ghec: '*'
type: how_to
topics:
- Security advisories
- Vulnerabilities
shortTitle: Create repository advisories
ms.openlocfilehash: d4b47f84b20873e97b18106448b768288fff3039
ms.sourcegitcommit: fcf3546b7cc208155fb8acdf68b81be28afc3d2d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2022
ms.locfileid: "145095647"
---
Qualquer pessoa com permissões de administrador em um repositório pode criar uma consultoria de segurança.

{% data reusables.security-advisory.security-researcher-cannot-create-advisory %}

## Como criar um aviso de segurança

{% data reusables.repositories.navigate-to-repo %} {% data reusables.repositories.sidebar-security %} {% data reusables.repositories.sidebar-advisories %}
4. Clique em **Nova consultoria de segurança de rascunho**.
  ![Botão Abrir consultoria de rascunho](/assets/images/help/security/security-advisory-new-draft-security-advisory-button.png)
5. Digite um título para sua consultoria de segurança.
{% data reusables.repositories.security-advisory-edit-details %} {% data reusables.repositories.security-advisory-edit-severity %} {% data reusables.repositories.security-advisory-edit-cwe-cve %} {% data reusables.repositories.security-advisory-edit-description %}
11. Clique em **Criar consultoria de segurança de rascunho**.
  ![Botão Criar consultoria de segurança](/assets/images/help/security/security-advisory-create-security-advisory-button.png)

## Próximas etapas

- Faça um comentário sobre o rascunho da consultoria de segurança para discutir a vulnerabilidade com sua equipe.
- Adicione colaboradores à consultora de segurança. Para obter mais informações, confira "[Como adicionar um colaborador a uma consultoria de segurança do repositório](/code-security/repository-security-advisories/adding-a-collaborator-to-a-repository-security-advisory)".
- Colaborar de modo particular com a correção da vulnerabilidade em uma bifurcação privada temporária. Para obter mais informações, confira "[Colaboração em um fork privado temporário para resolver uma vulnerabilidade de segurança do repositório](/code-security/repository-security-advisories/collaborating-in-a-temporary-private-fork-to-resolve-a-repository-security-vulnerability)".
- Adicione indivíduos que deveriam receber crédito por contribuírem para a consultoria de segurança. Para obter mais informações, confira "[Como editar uma consultoria de segurança do repositório](/code-security/repository-security-advisories/editing-a-repository-security-advisory#about-credits-for-security-advisories)".
- Publicar a consultoria de segurança para notificar a sua comunidade sobre a vulnerabilidade de segurança. Para obter mais informações, confira "[Como publicar uma consultoria de segurança do repositório](/code-security/repository-security-advisories/publishing-a-repository-security-advisory)".
