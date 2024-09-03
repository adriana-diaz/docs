This guide will walk you through publishing an API REST application to Azure using Visual Studio 2019. We will cover the steps from creating a Resource Group, App Service, and SQL Database to deploying your application.

## Prerequisites

- Visual Studio 2019 installed
- Azure account
- API REST project ready to deploy

## Step 1: Create a Resource Group

A Resource Group in Azure is a container that holds related resources for an Azure solution.

1. Log in to the [Azure Portal](https://portal.azure.com).
2. Search in menu, click on **Resource groups**.
3. Click on **+ Add** at the top.
4. Fill in the necessary details:
   - **Subscription**: Select your Azure subscription.
   - **Resource Group**: Enter a name for your Resource Group.
   - **Region**: Choose the region closest to your users.
5. Click **Review + create**, then **Create**.

## Step 2: Create a SQL Database and Server

1. In the Azure Portal, go to the **SQL Databases**.
2. Click on **+ Add** at the top.
3. Fill in the necessary details:
   - **Subscription**: Select your Azure subscription.
   - **Resource Group**: Select the Resource Group you created earlier.
   - **Database name**: Enter a name for your database.
   - **Server**: Click on **Create new** to create a new SQL Server.
     - **Server name**: Enter a unique name for your server.
     - **Server admin login**: Enter an admin username.
     - **Password**: Enter a strong password.
     - **Location**: Choose the same region as your Resource Group.
   - **Compute + storage**: Select a pricing tier that suits your needs.
4. Click **Review + create**, then **Create**.

## Step 3: Connect Your Visual Studio Project to the Database using LINQ

1. In Visual Studio, open your API REST project.
2. Ensure that you've installed the necessary NuGet package to set up your LINQ to SQL connection, which will generate the `.dmlb` file.
3. Open **Server Explorer** in Visual Studio.
4. Right-click on **Data Connections** and select **Add Connection**.
5. In the **Server name** field, enter your Azure SQL Server name (e.g., `yourserver.database.windows.net`).
6. Enter the credentials you set up when creating the server, and ensure that you select the option to trust the server.
7. Choose the database you want to connect to from the list.
8. Once connected, drag and drop the stored procedures (SP) you need from **Server Explorer** onto your LINQ to SQL classes.

This process will automatically integrate your database and stored procedures with your LINQ to SQL model, enabling your project to interact with the Azure SQL Database.

## Step 4: Publish Your API REST Application from Visual Studio 2019

1. Right-click on your project in **Solution Explorer** and select **Publish**.
2. In the **Pick a publish target** window, select **Azure** and then **Azure App Service (Windows)**.
3. Click **Next**.
4. Choose **Select existing** and click **Next**.
5. Sign in to your Azure account if prompted.
6. Select the App Service you created earlier and click **Finish**.
7. Review the settings in the **Publish** window and click **Publish**.

## Step 5: Verify the Deployment

1. After the deployment is complete, Visual Studio will open a browser window to your app's URL.
2. Verify that your API is running as expected and that it can interact with your Azure SQL Database.
3. Perform your tests using Postman. For example, you can test your stored procedures (SP) using an endpoint like `https://yourwebappname.azurewebsites.net/api/usuario/ingresarusuario`.
