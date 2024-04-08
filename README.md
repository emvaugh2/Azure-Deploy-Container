# Build and Run a Container Using Azure ACR Tasks

**There are 4 objectives with this lab:**
* Start Cloud Shell
* Create a New Container Registry
* Build an Image and Push to ACR
* Run the New Container


## Start Cloud Shell

I want to start this lab off by saying I didn't know how to do this lab at all so I resorted to watching the walkthrough and go through the text guide. All the commands are sourced from the walkthrough but I chose to modify them and explain each part of the command so show full understanding of whats happening. So with that being said, lets start this lab!

In the first part of the lab, we'll need to get the Azure Cloud Shell up and running. We've done this plenty of times so no walkthrough here. Use Bash and make sure the location matches the location of the storage account in your resource group (RG) though. 

Once your Cloud Shell is up,  that completes the first objective of this lab! On to objective 2. 

## Create a New Container Registry

For the second portion of this lab, we're going to the container registry using Azure Cloud Registry (ACR). So the first thing I did was create a variable for both my resource group and the name of my container registry since we'll need to refer to these values in the following commands. It's only three commands but this just makes it easier to not make mistakes. 

![Image](AzureCreateACR1.png)

Once that's completed, we'll use the following command to create the ACR. The ACR is where we'll store the containers. Think of it as a warehouse where we can put boxes (or literal containers). We can call upon it to find a repository or container. We're just choosing to store it here. The command is: 
`az acr create --resource-group $RG \ --name $ACR \
--sku Basic \
--admin-enabled true`



That completes the second objective. Lets move to the 3rd one. 

## Build an Image and Push to ACR

Now, we have to create the image gallery, definition, and version for the virtual machine scale set (VMSS) to be built from. All of these properties will come from the `linVM` we just used in the portal. So I used a website to find all the commands for each resource ([link here](https://learn.microsoft.com/en-us/cli/azure/sig?view=azure-cli-latest)). You can find all the commands there. 

![Image](AzureCustomVMSS3.png)



Now we're done with Objective 3. Lets move on to the final objective. 

## Run the New Container

Now, we need to create the VMSS from the image gallery that we've created. Lets revisit the `$IMAGE` variable and give it a new value. Navigate to the image definition resource. Go to Settings > Properties and then copy its Resource ID. We're going to use this value as the new `$IMAGE` value. 

![Image](AzureCustomVMSS10.png)



Lab completed!

## Personal Notes



