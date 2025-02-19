---
title: Action Network
description: Documentation for the Action Network node in n8n, a workflow automation platform. Includes details of operations and configuration, and links to examples and credentials information.
contentType: integration
---

# Action Network



Use the Action Network node to automate work in Action Network, and integrate Action Network with other applications. n8n has built-in support for a wide range of Action Network features, including creating, updating, and deleting events, people, tags, and signatures. 

On this page, you'll find a list of operations the Action Network node supports, and links to more resources.

/// note | Credentials
Refer to [Action Network credentials](/integrations/builtin/credentials/actionnetwork/) for guidance on setting up authentication. 
///
/// note | Examples and templates
For usage examples and templates to help you get started, take a look at n8n's [Action Network integrations](https://n8n.io/integrations/action-network/){:target="_blank" .external-link} list.
///

## Basic operations

* Attendance
    * Create
    * Get
    * Get All
* Event
    * Create
    * Get
    * Get All
* Person
    * Create
    * Get
    * Get All
    * Update
* Person Tag
    * Add
    * Remove
* Petition
    * Create
    * Get
    * Get All
    * Update
* Signature
    * Create
    * Get
    * Get All
    * Update
* Tag
    * Create
    * Get
    * Get All

## Example

This workflow allows you to create a new event in Action Network, then create a new person and mark them as having attended your event. This workflow uses the following two nodes.
- [Start](/integrations/builtin/core-nodes/n8n-nodes-base.start/)
- [ActiveCampaign]()

The final workflow should look like the following image.

![A workflow with the Action Network node](/_images/integrations/builtin/app-nodes/actionnetwork/workflow.png)

### 1. Start node

The start node exists by default when you create a new workflow.

### 2. Action Network node

1. First enter your credentials. You can find out how to do that [here](/integrations/builtin/credentials/actionnetwork/).
2. Fill in the remaining parameters as follows:
    * **Resource**: Select **Event** from the dropdown list.
    * **Operation**: Select **Create** from the dropdown list.
    * **Origin System**: Enter where this event originated. n8n.io in our example.
    * **Title**: Enter the name of your event, July Meetup in our example here.
3. Enable the **Simple** toggle to return an easier to view response as opposed to the complete raw data.
4. Use the **Additional Fields** to enter any further details about your event. Here we provided the Start Date.

![Action Network node](/_images/integrations/builtin/app-nodes/actionnetwork/action_network_node.png)

### 3. Action Network1 node

1. First enter your credentials. You can find out how to do that [here](/integrations/builtin/credentials/actionnetwork/).
2. Fill in the remaining parameters as follows:
    * **Resource**: Select **Person** from the dropdown list.
    * **Operation**: Select **Create** from the dropdown list.
3. Enable the **Simple** toggle to return an easier to view response as opposed to the complete raw data.
4. In the **Email Address** section, enter the address and status for this person (here we Subscribe them).
5. Use the **Additional Fields** to enter any further details about this person. Here we provided their given name.

![Action Network1 node](/_images/integrations/builtin/app-nodes/actionnetwork/action_network_node1.png)

### 4. Action Network2 node

1. First enter your credentials. You can find out how to do that [here](/integrations/builtin/credentials/actionnetwork/).
2. Fill in the remaining parameters as follows:
    * **Resource**: Select **Attendance** from the dropdown list.
    * **Operation**: Select **Create** from the dropdown list.
    * **Person ID**: Enter the ID for the person created by the previous node.
    * **Event ID**: Enter the ID for the event created in the first node.
3. Enable the **Simple** toggle to return an easier to view response as opposed to the complete raw data.

![Action Network2 node](/_images/integrations/builtin/app-nodes/actionnetwork/action_network_node2.png)

