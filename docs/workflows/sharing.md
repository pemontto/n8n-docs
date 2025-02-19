---
description: Share workflows between users.
contentType: howto
---

# Workflow sharing

Workflow sharing allows you to share workflows between users of the same n8n instance.

## Share a workflow

1. Open the workflow you want to share.
2. Select **Share**.
3. In **Add users**, find and select the users you want to share with.
4. Select **Save**.

## View shared workflows

You can browse and search workflows on the **Workflows** list.

* **All workflows** lists all workflows you can access. This includes:
	* Your own workflows.
	* Workflows shared with you.
	* If you are logged in as instance owner: all workflows in the instance.
* **My workflows**: workflows you created.

## Workflow roles and permissions

There are two workflow roles: owner and editor. The owner is the user who created the workflow. Editors are other users with access to the workflow.

You can't change the workflow owner, except when deleting the user.

/// note | Credentials
Workflow sharing allows editors to use all credentials used in the workflow. This includes credentials that aren't explicitly shared with them using [credential sharing](/credentials/credential-sharing/).
///
### Permissions

| Permissions | Owner | Editor | 
| ----------- | ----- | ------ | 
| View workflow (read-only) | :white_check_mark: | :white_check_mark: |
| View executions | :white_check_mark: | :white_check_mark: |
| Update (including tags) | :white_check_mark: | :white_check_mark: |
| Run | :white_check_mark: | :white_check_mark: |
| Share | :white_check_mark: | :x: |
| Export | :white_check_mark: | :white_check_mark: |
| Delete | :white_check_mark: | :x: |

## Node editing restrictions with unshared credentials

Sharing in n8n works on the principle of least privilege. This means that if a user shares a workflow with you, but they don't share their credentials, you can't edit the nodes within the workflow that use those credentials. You can view and run the workflow, and edit nodes that don't use unshared credentials.

Refer to [Credential sharing](/credentials/credential-sharing/) for guidance on sharing credentials.
