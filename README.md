# erp eForm  

[Run and Debug](#run-and-debug)  

- [Checkout](#checkout)  
- [Debug api](#debug-api)
- [VS Code Extension](#vs-code-extension)
- [Run UI](#run-ui)
- [Debug UI](#debug-ui)

[Add New Form](#add-new-form)

- [API::SharedEformData](#sharedeformdata)
  - [Entities](#entities)
  - [Repositories](#repositories)
  - [Services](#services)
  - [SharedEformData.projitems](#sharedeformdataprojitems)

- [API::GraphQL](#graphql)
  - [Mutations](#mutations)
  - [Queries](#queries)
  - [Types](#types)

- [API::Startup](#startup)
- [API::Controller](#controller)
- [UI::Generate Application](#generate-application)
- [UI::AppImportModules](#appimportmodules)
- [UI::GraphQL Query](#ui-graphql-query)
- [UI::GraphQL Config](#ui-graphql-config)
- [UI::NPM Script](#ui-npm-script)
- [UI::Named GraphQL Client](#ui-named-graphql-client)
- [UI::Get Data](#ui-get-data)
- [API::TestAuthHandler](#test-auth-handler)

## Run and Debug

### Checkout

```git
git clone https://github.com/gammonconstruction/erp.eform
cd erp.eform
git submodule update --init
```

![image](https://user-images.githubusercontent.com/48709072/142964803-91025e43-882a-4b44-9958-636b631a6dba.png)

### Debug api

```dotnet
dotnet restore
dotnet dev-certs https --trust  
```

![image](https://user-images.githubusercontent.com/48709072/142965291-e55986f4-db73-4bf6-a9f4-6bc3442eadc6.png)

*dotnet run --project api  
*close all browser to apply trust  
*vscode: ctrl+shift+p => Select Project => erp.eform  

### VS Code Extension

![image](https://user-images.githubusercontent.com/48709072/142976152-2fca2d74-1975-435c-951f-8522d597256c.png)

### Run UI

```nodejs
cd  ui\ClientApp
npm install -g @angular/cli  
npm install
```

![image](https://user-images.githubusercontent.com/48709072/142976225-1adb7691-1d6c-4c67-a61f-deca8d789729.png)

*ng serve --project eform  
*first time will take time to compiling es2015 as esm2015 for node_modules

### Debug UI

![image](https://user-images.githubusercontent.com/48709072/142976270-7a2fd70a-174b-4148-8129-d13e0d4217ce.png)

## Add new form

### SharedEformData

- #### Entities

  ![image](https://user-images.githubusercontent.com/48709072/142982314-88968ba7-491c-4abb-8b16-6e62e9462eca.png)

- #### Repositories

  ![image](https://user-images.githubusercontent.com/48709072/142982370-48cece39-d1cf-4d95-a8ae-70453020af07.png)
  
- #### Services

  ![image](https://user-images.githubusercontent.com/48709072/142982411-8ca36c09-1d73-4510-a7e9-40e9fd8a24c8.png)

- #### SharedEformData.projitems

  ![image](https://user-images.githubusercontent.com/48709072/142983265-e640896d-ccff-4f2a-a7c3-14cf91b8c854.png)

### GraphQL

- #### Mutations

  ![image](https://user-images.githubusercontent.com/48709072/142982411-8ca36c09-1d73-4510-a7e9-40e9fd8a24c8.png)

- #### Queries

  ![image](https://user-images.githubusercontent.com/48709072/142985909-c93126b5-4df0-4f61-a54a-4952e2b52cac.png)

- #### Types

  ![image](https://user-images.githubusercontent.com/48709072/142986001-c9dd91d4-9271-44be-b450-60d92f2e9165.png)

### Startup

  ![image](https://user-images.githubusercontent.com/48709072/142996010-267912d6-035c-420b-ac82-01cbbd9dec1c.png)

### Controller

  ![image](https://user-images.githubusercontent.com/48709072/142990932-76a583be-e06c-41b9-a5ad-0c60ebe09693.png)

### Generate Application

  ![image](https://user-images.githubusercontent.com/48709072/142992016-a0cfb62e-ee94-4e73-9cea-5cca05a34b91.png)

  *ng generate application csdpe --prefix=csdpe

### AppImportModules

  ![image](https://user-images.githubusercontent.com/48709072/142992480-dc8ab3ed-cd56-4fad-addc-fdac1937d32b.png)

### UI GraphQL Query

  ![image](https://user-images.githubusercontent.com/48709072/142993052-82f12c83-5772-417a-ab1e-f02fc65432a3.png)

  *update formData properties

### UI GraphQL Config

![image](https://user-images.githubusercontent.com/48709072/142997110-3ef4b76f-de88-446c-832c-a18f06f86707.png)

### UI NPM Script

![image](https://user-images.githubusercontent.com/48709072/142994209-26bd9595-fd29-4b3f-b635-b0e133ad23bd.png)

```json
{
    "download-schema:csdpe": "curl --ntlm --negotiate -u: https://localhost:5001/graphql/csdpe?sdl -o ./libraries/eform-graphql-api/src/lib/generated/schemas/csdpe.graphql",
    "codegen:csdpe": "npm run download-schema:csdpe && set NODE_TLS_REJECT_UNAUTHORIZED=0&& graphql-codegen --config libraries/eform-graphql-api/src/lib/config/csdpe.yml",
}
```

### UI Export Client

![image](https://user-images.githubusercontent.com/48709072/142996891-ab993410-c224-4b41-9ddd-c19e55345f14.png)

### UI Named GraphQL Client

![image](https://user-images.githubusercontent.com/48709072/143010640-8cfc3326-288d-40fc-a2e7-5977645975af.png)

### UI Get Data

![image](https://user-images.githubusercontent.com/48709072/143011899-47dfc784-149d-44dd-8cec-0271c60608d5.png)

### Test Auth Handler
