---
wts:
    title: '08 - Implement Azure Functions (5 min)'
    module: 'Module 03: Describe core solutions and management tools'
---
# 08 - Implement Azure Functions (5 min)

In this walkthrough, we will create a Function App to display a Hello message when there is an HTTP request. 

# Task 1: Create a Function app 

In this task, we will create a Function app.

1. Sign in to the [Azure portal](https://portal.azure.com).

2. In the **Search** bar at the top of the portal, search for and select **Function App** and then, from the **Function App** blade, click **+ Create**.

3. On the **Create Function App** blade, under the **Select a hosting option**, select the **Consumption** checkbox and then click **Select**.

4. On the **Basic** tab of the **Function App** blade, specify the following settings (replace **xxxx** in the name of the function with letters and digits such that the name is globally unique and leave all other settings with their default values): 

    | Settings | Value |
    | -- | --|
    | Subscription | **Keep default supplied** |
    | Resource group | **Create new resource group** |
    | Function App name | **function-xxxx** |
    | Runtime stack | **.NET** |
    | Version | **8 (LTS), in process model** |
    | Region | **East US** |
    | Operating System | **Windows** | 

    **Note** - Remember to change the **xxxx** so that it makes a unique **Function App name**

5. Click **Review + Create** and, after successful validation, click **Create** to begin provisioning and deploying your new Azure Function App.

6. Wait for the notification that the resource has been created.

7. When the deployment has completed, click **Go to resource** from the deployment blade. Alternatively, navigate back to the **Function App** blade, click **Refresh** and verify that the newly created function app has the **Running** status. 

    ![Screenshot of the Function App page with the new Function app.](../images/0701.png)

# Task 2: Create a HTTP triggered function and test

In this task, we will use the Webhook + API function to display a message when there is an HTTP request. 

1. On the **Function App** blade, click the newly created function app. 

2. On the function app blade, in the **Overview** section, click the **Functions** tab and under **Create in Azure portal**, select **Create function**.

    ![Screenshot of the choose a development environment step in the azure functions for dot net getting started pane inside Azure portal. The display elements for creating a new in-portal function are highlighted. The highlighted elements are expand the function app, add new function, in-portal, and the continue button.](../images/0702.png)

3. A **Create function** pop-up window will appear on the right. In the **Select a template** section click **HTTP trigger**. Click **Next**.

    ![Screenshot of the create a function step in the azure functions for dot net getting started pane inside Azure portal. The HTTP trigger card is highlighted to illustrate the display elements used to add a new webhook to an Azure function.](../images/0702a.png)

4. On the **Template details** tab of the **Create function** pop-up window, leave the default settings and click **Create**.    

5. You should now be automatically redirected to the newly created function's **Code + Test** page. If not, click on the **HttpTrigger1** function on the **Overview** page of the **Function App** blade.

6. On the **Code + Test** blade, review the auto-generated code and note that the code is designed to run an HTTP request and log information. Also, notice the function returns a Hello message with a name. 

    ![Screenshot of the function code. The Hello message is hightlighted.](../images/0704.png)

7. Click **Get function URL** from the top section of function editor. 

8. Locate the **default (Host key)** URL and select the **Copy to Clipboard** symbol to copy the URL.

    ![Screenshot of the get function URL pane inside the function editor in Azure portal. The display elements get function URL button, set key dropdown, and copy URL button are highlighted to indicate how to obtain and copy the function URL from the function editor.](../images/0705.png)

9. Open a new browser tab and paste the copied function URL into your web browser's address bar. When the page is requested the function will run. Notice the returned message stating that the function requires a name in the request body.

    ![Screenshot of the please provide a name message.](../images/0706.png)

10. Append **&name=*yourname*** to the end of the URL.

    **Note**: For example, if your name is Cindy, the final URL will resemble the following: `https://azfuncxxx.azurewebsites.net/api/HttpTrigger1?code=X9xx9999xXXXXX9x9xxxXX&name=cindy`

    ![Screenshot of a highlighted function URL and an appended example user name in the address bar of a web browser. The hello message and user name are also highlighted to illustrate the output of the function in the main browser window.](../images/0707.png)

11. When you hit enter, your function runs and every invocation is traced. To view the traces, return to the Portal **HttpTrigger1 \| Code + Test** blade and click **Invocations**. You can **configure** Application Insights by selecting the timestamp and click **Run query in Application Insights**.

    ![Screenshot of a trace information log resulting from running the function inside the function editor in Azure portal.](../images/0709.png) 

Congratulations! You have created a Function App to display a Hello message when there is an HTTP request.  

**Note**: To avoid additional costs, you can optionally remove this resource group. Search for resource groups, click your resource group, and then click **Delete resource group**. Verify the name of the resource group and then click **Delete**. Monitor the **Notifications** to see how the delete is proceeding.
