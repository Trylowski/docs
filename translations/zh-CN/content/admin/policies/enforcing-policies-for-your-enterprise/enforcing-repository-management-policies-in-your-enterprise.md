---
title: 在企业中实施仓库管理策略
intro: 您可以在企业组织内执行仓库管理策略，或允许在每个组织中设置策略。
permissions: Enterprise owners can enforce policies for repository management in an enterprise.
redirect_from:
  - /enterprise/admin/installation/configuring-the-default-visibility-of-new-repositories-on-your-appliance
  - /enterprise/admin/guides/user-management/preventing-users-from-changing-a-repository-s-visibility
  - /enterprise/admin/user-management/preventing-users-from-changing-a-repositorys-visibility
  - /enterprise/admin/user-management/restricting-repository-creation-in-your-instance
  - /enterprise/admin/user-management/preventing-users-from-deleting-organization-repositories
  - /enterprise/admin/installation/setting-git-push-limits
  - /enterprise/admin/guides/installation/git-server-settings
  - /enterprise/admin/articles/setting-git-push-limits
  - /enterprise/admin/user-management/allowing-admins-to-enable-anonymous-git-read-access-to-public-repositories
  - /enterprise/admin/installation/disabling-the-merge-conflict-editor-for-pull-requests-between-repositories
  - /enterprise/admin/developer-workflow/blocking-force-pushes-on-your-appliance
  - /enterprise/admin/developer-workflow/blocking-force-pushes-to-repositories-owned-by-a-user-account-or-organization
  - /enterprise/admin/developer-workflow/blocking-force-pushes-to-a-repository
  - /enterprise/admin/articles/blocking-force-pushes-on-your-appliance
  - /enterprise/admin/guides/user-management/preventing-users-from-changing-anonymous-git-read-access-to-a-repository
  - /enterprise/admin/user-management/preventing-users-from-changing-anonymous-git-read-access
  - /enterprise/admin/articles/blocking-force-pushes-to-a-repository
  - /enterprise/admin/articles/block-force-pushes
  - /enterprise/admin/articles/blocking-force-pushes-for-a-user-account
  - /enterprise/admin/articles/blocking-force-pushes-for-an-organization
  - /enterprise/admin/articles/blocking-force-pushes-to-repositories-owned-by-a-user-account-or-organization
  - /enterprise/admin/developer-workflow/blocking-force-pushes
  - /enterprise/admin/policies/enforcing-repository-management-policies-in-your-enterprise
  - /admin/policies/enforcing-repository-management-policies-in-your-enterprise
  - /articles/enforcing-repository-management-settings-for-organizations-in-your-business-account
  - /articles/enforcing-repository-management-policies-for-organizations-in-your-enterprise-account
  - /articles/enforcing-repository-management-policies-in-your-enterprise-account
  - /github/setting-up-and-managing-your-enterprise-account/enforcing-repository-management-policies-in-your-enterprise-account
  - /github/setting-up-and-managing-your-enterprise/enforcing-repository-management-policies-in-your-enterprise-account
  - /github/setting-up-and-managing-your-enterprise/setting-policies-for-organizations-in-your-enterprise-account/enforcing-repository-management-policies-in-your-enterprise-account
versions:
  ghec: '*'
  ghes: '*'
  ghae: '*'
type: how_to
topics:
  - Enterprise
  - Policies
  - Repositories
  - Security
shortTitle: Repository management policies
ms.openlocfilehash: 10b34ef1d0049ca68e1b0ec655f9d6351c06d396
ms.sourcegitcommit: 6185352bc563024d22dee0b257e2775cadd5b797
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2022
ms.locfileid: '148192639'
---
## 关于企业中的仓库管理策略

您可以执行策略来控制企业在 {% data variables.product.product_name %} 上的企业成员如何管理仓库。 您也可以允许组织所有者管理仓库管理策略。 有关详细信息，请参阅“[创建和管理存储库](/repositories/creating-and-managing-repositories)”以及“[组织和团队](/organizations)”。

{% ifversion ghes or ghae %}

## 配置新仓库的默认可见性

每次有人在您的企业上创建新仓库时，此人必须选择仓库的可见性。 当您配置企业的默认可见性设置时，需要选择默认可见性。 有关存储库可见性的详细信息，请参阅“[关于存储库](/repositories/creating-and-managing-repositories/about-repositories#about-repository-visibility)”。

如果企业所有者不允许成员创建某种类型的仓库，成员将无法创建此类仓库，即使可见性设置默认为此类型。 有关详细信息，请参阅“[强制实施用于存储库创建的策略](#enforcing-a-policy-for-repository-creation)”。

{% data reusables.enterprise-accounts.access-enterprise %} {% ifversion ghes or ghae %} {% data reusables.enterprise-accounts.policies-tab %} {% else %} {% data reusables.enterprise-accounts.settings-tab %} {% endif %} {% data reusables.enterprise-accounts.options-tab %}
1. 在“默认仓库可见性”下，使用下拉菜单并选择默认可见性。
  ![用于选择企业的默认存储库可见性的下拉菜单](/assets/images/enterprise/site-admin-settings/default-repository-visibility-settings.png)

{% data reusables.enterprise_installation.image-urls-viewable-warning %}

{% endif %}

## 强制实施针对基本存储库权限的策略

在企业帐户拥有的所有组织中，你可以为组织成员设置基本存储库权限级别（无、读取、写入或管理），或允许所有者在组织级别管理设置。

{% data reusables.enterprise-accounts.access-enterprise %} {% data reusables.enterprise-accounts.policies-tab %} {% data reusables.enterprise-accounts.repositories-tab %}
4. 在“基本权限”（团队讨论）下，审查有关更改设置的信息。 {% data reusables.enterprise-accounts.view-current-policy-config-orgs %}
5. 在“基本权限”下，使用下拉菜单并选择策略。
  ![包含存储库权限策略选项的下拉菜单](/assets/images/help/business-accounts/repository-permissions-policy-drop-down.png)


## 执行仓库创建策略

在企业拥有的所有组织中，您可以允许成员创建仓库、将仓库创建限于组织所有者或允许所有者在组织级别管理设置。 

如果允许成员在组织中创建存储库，可选择成员可以创建的存储库类型（公共、专用和内部）。

{% ifversion enterprise-namespace-repo-setting %} {% ifversion ghec %}如果企业使用 {% data variables.product.prodname_emus %}，{% else %}{% endif %}还可以阻止用户创建其用户帐户拥有的存储库。
{% endif %}

{% data reusables.repositories.internal-repo-default %} 有关内部存储库的更多信息，请参阅[创建内部存储库](/articles/creating-an-internal-repository)。

{% data reusables.organizations.repo-creation-constants %}

{% data reusables.enterprise-accounts.access-enterprise %} {% data reusables.enterprise-accounts.policies-tab %} {% data reusables.enterprise-accounts.repositories-tab %}
5. 在“Repository creation”下，检查有关更改设置的信息。 {% data reusables.enterprise-accounts.view-current-policy-config-orgs %} {% data reusables.enterprise-accounts.repo-creation-policy %} {% data reusables.enterprise-accounts.repo-creation-types %}{% ifversion enterprise-namespace-repo-setting %}
1. （可选）{% ifversion ghec %}如果企业使用 {% data variables.product.prodname_emus %}，并且你{% endif %}要阻止企业成员创建其用户帐户拥有的存储库，请选择“阻止创建用户命名空间存储库”。
  ![显示分支策略中已禁用选项列表的屏幕截图](/assets/images/help/business-accounts/restrict-personal-namespace-enabled-setting.png){% endif %}

## 实施有关复刻私有或内部仓库的策略
在企业拥有的所有组织中，您可以允许有权访问私有或内部仓库的人员复刻仓库、永远不允许分支私有或内部仓库，或者允许所有者在组织级别管理设置。

{% ifversion org-owners-limit-forks-creation %} 具有管理员权限的人员可以设置更精细的分支策略。 有关详细信息，请参阅“[管理组织的分支策略](/organizations/managing-organization-settings/managing-the-forking-policy-for-your-organization)”。
{% endif %}

{% ifversion enterprise-namespace-repo-setting %} {% note %}

注意：如果{% ifversion ghec %}企业使用 {% data variables.product.prodname_emus %}，并且{% endif %}你的“存储库创建”策略阻止企业成员创建其用户帐户拥有的存储库，则无论“存储库分支”策略如何，都不会允许成员在其用户帐户中为存储库创建分叉。

{% endnote %} {% endif %}

{% data reusables.enterprise-accounts.access-enterprise %} {% data reusables.enterprise-accounts.policies-tab %} {% data reusables.enterprise-accounts.repositories-tab %}
1. 在“Repository forking”（仓库复刻）下，审查有关更改设置的信息。 {% data reusables.enterprise-accounts.view-current-policy-config-orgs %}
2. 在“存储库分支”下，使用下拉菜单并选择策略。

  ![带有存储库分支策略选项的下拉菜单](/assets/images/help/business-accounts/repository-forking-policy-drop-down.png){% ifversion innersource-fork-policies %}
5. 如果启用了分叉，则可以指定允许用户创建存储库分支的位置。 查看有关更改设置的信息并选择策略。

    ![显示存储库分支策略选项列表的屏幕截图](/assets/images/help/business-accounts/repository-forking-policy-settings.png){% endif %}
  
## 执行邀请{% ifversion ghec %} 外部{% endif %} 协作者参与仓库的策略

在你的企业拥有的所有组织中，你可以允许成员邀请{% ifversion ghec %}外部{% endif %}协作者到存储库、限制{% ifversion ghec %}外部协作者{% endif %}对组织所有者的邀请、{% ifversion prevent-org-admin-add-outside-collaborator %}限制{% ifversion ghec %}外部协作者{% endif %}对企业所有者的邀请、{% endif %}或允许组织所有者管理组织级别的设置。

{% data reusables.enterprise-accounts.access-enterprise %} {% data reusables.enterprise-accounts.policies-tab %} {% data reusables.enterprise-accounts.repositories-tab %}
3. 在“仓库 {% ifversion ghec %}外部协作者{% elsif ghes or ghae %}邀请{% endif %}”下，请查看有关更改设置的信息。 {% data reusables.enterprise-accounts.view-current-policy-config-orgs %}
4. 在“仓库 {% ifversion ghec %}外部协作者{% elsif ghes or ghae %}邀请{% endif %}”下，使用下拉菜单并选择策略。

  {% ifversion ghec %} ![带有外部协作者邀请策略选项的下拉菜单](/assets/images/help/business-accounts/repository-invitation-policy-drop-down.png) {% elsif ghes or ghae %} ![带有邀请策略选项的下拉菜单](/assets/images/enterprise/business-accounts/repository-invitation-policy-drop-down.png)  
  {% endif %}

## 对默认分支名称实施策略

在企业拥有的所有组织中，您可以为成员创建的任何新仓库设置默认分支名称。 您可以选择在所有组织中强制实施默认分支名称，或允许个别组织设置不同的名称。

{% data reusables.enterprise-accounts.access-enterprise %} {% data reusables.enterprise-accounts.policies-tab %}
3. 在“存储库策略”选项卡的“默认分支名称”下，输入新存储库应使用的默认分支名称。
    ![输入默认分支名称的文本框](/assets/images/help/business-accounts/default-branch-name-text.png)
4. （可选）要对企业中的所有组织强制实施默认分支名称，请选择“在整个企业中实施”。
    ![强制实施复选框](/assets/images/help/business-accounts/default-branch-name-enforce.png)
5. 单击“更新”。
    ![“更新”按钮](/assets/images/help/business-accounts/default-branch-name-update.png)

## 执行更改仓库可见性的策略

在您的企业拥有的所有组织中，您可以允许具有管理员权限的成员更改仓库的可见性、将仓库可见性更改限制为组织所有者或允许所有者在组织级别管理设置。 当您阻止成员更改仓库可见性时，只有企业所有者可以更改仓库的可见性。

如果企业所有者仅允许组织所有者创建仓库，则成员将无法更改仓库可见性。 如果企业所有者只允许私有仓库成员创建私有仓库，则成员只能将仓库的可见性更改为私有。 有关详细信息，请参阅“[强制实施用于存储库创建的策略](#enforcing-a-policy-for-repository-creation)”。

{% data reusables.enterprise-accounts.access-enterprise %} {% data reusables.enterprise-accounts.policies-tab %} {% data reusables.enterprise-accounts.repositories-tab %}
1. 在“Repository visibility change”下，检查有关更改设置的信息。 {% data reusables.enterprise-accounts.view-current-policy-config-orgs %}
1. 在“Repository visibility change（仓库可见性更改）”下，使用下拉菜单选择策略。
   ![包含存储库可见性策略选项的下拉菜单](/assets/images/help/business-accounts/repository-visibility-policy-drop-down.png)

## 执行仓库删除和转移的策略

在您的企业拥有的所有组织中，您可以允许具有管理员权限的成员删除或转让仓库、将仓库删除和转让限制为组织所有者或允许所有者在组织级别管理设置。

{% data reusables.enterprise-accounts.access-enterprise %} {% data reusables.enterprise-accounts.policies-tab %} {% data reusables.enterprise-accounts.repositories-tab %}
5. 在“Repository deletion and transfer”下，检查有关更改设置的信息。 {% data reusables.enterprise-accounts.view-current-policy-config-orgs %}

{% data reusables.enterprise-accounts.repository-deletion-policy %}

## 执行删除议题的策略

在您的企业拥有的所有组织中，您可以允许具有管理员权限的成员删除仓库中的议题、将议题删除限制为组织所有者或允许所有者在组织级别管理设置。

{% data reusables.enterprise-accounts.access-enterprise %} {% data reusables.enterprise-accounts.policies-tab %}
3. 在“存储库策略”选项卡中的“存储库问题删除”下，查看有关更改设置的信息。 {% data reusables.enterprise-accounts.view-current-policy-config-orgs %}
4. 在“Repository issue deletion（仓库议题删除）”下，使用下拉菜单并选择策略。

  ![带有问题删除策略选项的下拉菜单](/assets/images/help/business-accounts/repository-issue-deletion-policy-drop-down.png)

{% ifversion ghes or ghae %}

## 执行 Git 推送限制策略

要使仓库大小保持可管理并防止发生性能问题，可以为企业中的仓库配置文件大小限制。

默认情况下，强制执行仓库上传限制时，无法添加或上传超过 100 MB 的文件。

{% data reusables.enterprise-accounts.access-enterprise %} {% data reusables.enterprise-accounts.policies-tab %} {% data reusables.enterprise-accounts.options-tab %}
4. 在“Repository upload limit”下，使用下拉菜单，然后单击最大对象大小。
![包含最大对象大小选项的下拉菜单](/assets/images/enterprise/site-admin-settings/repo-upload-limit-dropdown.png)
5. （可选）要对企业中的所有存储库实施最大上传限制，请选择“对所有存储库强制执行”
![“对所有存储库强制执行最大对象大小”选项](/assets/images/enterprise/site-admin-settings/all-repo-upload-limit-option.png)

{% ifversion profile-name-enterprise-setting %}

## 强制实施在存储库中显示成员名称的策略

在企业拥有的所有组织中，可以允许成员在公共和内部存储库的问题和拉取请求中查看评论作者的配置文件名称及其用户名。

![评论中显示的评论者个人资料名称](/assets/images/help/issues/commenter-full-name.png)

{% note %}

注意：当对企业中的所有存储库强制实施此策略时，它将替代专用存储库的组织设置。 有关详细信息，请参阅“[管理组织中成员姓名的显示](/organizations/managing-organization-settings/managing-the-display-of-member-names-in-your-organization)”。

{% endnote %}

{% data reusables.enterprise-accounts.access-enterprise %} {% data reusables.enterprise-accounts.policies-tab %} {% data reusables.enterprise-accounts.options-tab %}
4. 在“允许成员在公共和内部存储库中查看评论作者的配置文件名称”下，选择下拉菜单并单击一个策略。
![“选项”页的屏幕截图，其中突出显示了策略下拉菜单](/assets/images/enterprise/site-admin-settings/comment-authors-profile-name-drop-down.png)
5. （可选）要强制显示企业中所有存储库的配置文件名称，请选择“对实例上的所有存储库强制实施”。
![突出显示了“对所有存储库强制实施”选项的屏幕截图](/assets/images/enterprise/site-admin-settings/enforce-for-all-repositories-option.png)

{% endif %}

## 为仓库之间的拉取请求配置合并冲突编辑器

要求用户在其计算机上本地解决合并冲突可以避免用户因疏忽而从分叉写入到上游仓库。

{% data reusables.enterprise-accounts.access-enterprise %} {% ifversion ghes or ghae %} {% data reusables.enterprise-accounts.policies-tab %} {% else %} {% data reusables.enterprise-accounts.settings-tab %} {% endif %} {% data reusables.enterprise-accounts.options-tab %}
1. 在“存储库之间的拉取请求的冲突编辑器”下，使用下拉菜单，然后单击“已禁用”。
 ![包含用于禁用合并冲突编辑器的选项的下拉菜单](/assets/images/enterprise/settings/conflict-editor-settings.png)

## 配置强制推送

每个仓库从拥有该仓库的用户帐户或组织的设置继承默认强制推送设置。 每个组织和用户帐户都会从企业的强制推送设置继承默认强制推送设置。 如果您更改企业的强制推送设置，此策略适用于任何用户或组织拥有的所有仓库。

### 阻止强制推送到所有仓库

{% data reusables.enterprise-accounts.access-enterprise %} {% data reusables.enterprise-accounts.policies-tab %} {% data reusables.enterprise-accounts.options-tab %}
4. 在“强制推送”下，使用下拉菜单，然后单击“允许”、“阻止”或“阻止到默认分支”  。
![强制推送下拉菜单](/assets/images/enterprise/site-admin-settings/force-pushes-dropdown.png)
5. （可选）选择“对所有存储库强制实施”，这将替代强制推送的组织和存储库级别设置。

### 阻止特定仓库的强制推送

{% data reusables.enterprise_site_admin_settings.override-policy %}

{% data reusables.enterprise_site_admin_settings.sign-in %} {% data reusables.enterprise_site_admin_settings.access-settings %} {% data reusables.enterprise_site_admin_settings.repository-search %} {% data reusables.enterprise_site_admin_settings.click-repo %} {% data reusables.enterprise_site_admin_settings.admin-top-tab %} {% data reusables.enterprise_site_admin_settings.admin-tab %}
4. 在“推送和拉取”下，选择“阻止”或“阻止到默认分支”  。
   ![阻止强制推送](/assets/images/enterprise/site-admin-settings/repo/repo-block-force-pushes.png)

### 阻止对用户帐户或组织拥有的仓库进行强制推送

仓库从它们所属的用户帐户或组织继承强制推送设置。 反过来，用户帐户和组织从企业的强制推送设置继承其强制推送设置。

您可以通过配置用户帐户或组织的设置来覆盖默认的继承设置。

{% data reusables.enterprise_site_admin_settings.sign-in %} {% data reusables.enterprise_site_admin_settings.access-settings %} {% data reusables.enterprise_site_admin_settings.search-user-or-org %} {% data reusables.enterprise_site_admin_settings.click-user-or-org %} {% data reusables.enterprise_site_admin_settings.admin-top-tab %} {% data reusables.enterprise_site_admin_settings.admin-tab %}
5. 在“Force pushes”部分的“Repository default settings”下，选择
    - 阻止：阻止对所有分支进行强制推送。
    - 阻止到默认分支：仅阻止强制推送到默认分支。
  ![阻止强制推送](/assets/images/enterprise/site-admin-settings/user/user-block-force-pushes.png)
6. （可选）选择“对所有存储库强制实施”来替代存储库特定的设置。 注意，这不会替代企业范围的策略。
   ![阻止强制推送](/assets/images/enterprise/site-admin-settings/user/user-block-all-force-pushes.png)

{% endif %}

{% ifversion ghes %}

## 配置匿名 Git 读取访问

{% data reusables.enterprise_user_management.disclaimer-for-git-read-access %}

如果已为 {% data variables.location.product_location %} [启用专用模式](/enterprise/admin/configuration/enabling-private-mode)，则可以允许存储库管理员启用对公共存储库的匿名 Git 读取访问权限。

启用匿名 Git 读取允许用户在企业上为自定义工具绕过身份验证。 当你或存储库管理员为存储库启用此权限设置时，未经过身份验证的 Git 操作（和具有 {% data variables.product.product_name %} 的网络访问权限的任何人）将获得存储库的读取权限（无需身份验证）。

默认情况下，禁用匿名 Git 读取访问权限。{% ifversion ghes = 3.4 or ghes = 3.5 or ghes = 3.6 or ghes = 3.7 %}当升级到 {% data variables.product.product_name %} 3.6 或更高版本时，匿名 Git 读取访问权限将在应用程序级别自动禁用，并且端口 9418 上的 `git://` 连接将返回以下错误。

```
The unauthenticated git protocol on port 9418 is no longer supported.
```

{% ifversion ghes > 3.5 %}

如果希望在环境中支持未经身份验证的 Git 协议，则必须手动重新启用该功能。 升级后运行以下命令：

```ShellSession
$ sudo ghe-config app.gitauth.git-protocol true
$ sudo ghe-config-apply
```

{% endif %}

{% data variables.product.prodname_ghe_server %} 的未来版本中将完全移除匿名 Git 读取访问权限。 {% data variables.product.company_short %} 建议使用 SSH 而不是 Git 协议。 有关此更改的详细信息，请参阅 [{% data variables.product.prodname_blog %}](https://github.blog/2022-06-28-improving-git-protocol-security-on-github-enterprise-server)。

{% endif %}



如有必要，您可以通过锁定仓库的访问设置，阻止仓库管理员更改企业上仓库的匿名 Git 访问设置。 在您锁定仓库的 Git 读取权限设置后，只有站点管理员可以更改设置。

{% data reusables.enterprise_site_admin_settings.list-of-repos-with-anonymous-git-read-access-enabled %}

{% data reusables.enterprise_user_management.exceptions-for-enabling-anonymous-git-read-access %}

### 设置所有仓库的匿名 Git 读取访问

{% data reusables.enterprise-accounts.access-enterprise %} {% ifversion ghes or ghae %} {% data reusables.enterprise-accounts.policies-tab %} {% else %} {% data reusables.enterprise-accounts.settings-tab %} {% endif %} {% data reusables.enterprise-accounts.options-tab %}
4. 在“匿名 Git 读取权限”下，使用下拉菜单，并单击“已启用”。
![匿名 Git 读取权限下拉菜单显示菜单选项“已启用”和“已禁用”](/assets/images/enterprise/site-admin-settings/enable-anonymous-git-read-access.png)
3. 或者，如果要阻止存储库管理员为实例上的所有存储库更改匿名 Git 读取权限设置，请选择“阻止存储库管理员更改匿名 Git 读取权限”。
![选中复选框可阻止存储库管理员更改企业上所有存储库的匿名 Git 读取权限设置。](/assets/images/enterprise/site-admin-settings/globally-lock-repos-from-changing-anonymous-git-read-access.png)

### 设置特定仓库的匿名 Git 读取访问

{% data reusables.enterprise_site_admin_settings.access-settings %} {% data reusables.enterprise_site_admin_settings.repository-search %} {% data reusables.enterprise_site_admin_settings.click-repo %} {% data reusables.enterprise_site_admin_settings.admin-top-tab %} {% data reusables.enterprise_site_admin_settings.admin-tab %}
6. 在“危险区域”下的“启用匿名 Git 读取权限”旁边，单击“启用”。
![存储库站点管理员设置的危险区域中“启用匿名 Git 读取权限”下的“已启用”按钮](/assets/images/enterprise/site-admin-settings/site-admin-enable-anonymous-git-read-access.png)
7. 查看更改。 要确认，请单击“是，启用匿名 Git 读取权限”。
![在弹出窗口中确认匿名 Git 读取权限设置](/assets/images/enterprise/site-admin-settings/confirm-anonymous-git-read-access-for-specific-repo-as-site-admin.png)
8. 或者，如果要阻止存储库管理员为此存储库更改设置，请选择“阻止存储库管理员更改匿名 Git 读取权限”。
![选中复选框可阻止存储库管理员更改此存储库的匿名 Git 读取权限。](/assets/images/enterprise/site-admin-settings/lock_anonymous_git_access_for_specific_repo.png)

{% endif %}
