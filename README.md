# sample-nodejs

### Folder Structure
```
├── .gitignore
├── README.md
├── /api                                - Main folder that contains all the business-logic and code/project structure.
    ├── /clients                        - Contains third party services files like - firebase, axios, aws, these can be reuse as required.
        ├── axios.js
        ├── firebase.js
        ├── aws.js
        ├── elasticSearch.js
        ├── mysql.js
        ├── mondoDB.js
        ├── sequelize.js
    ├── /common                         - Contains common files of the project like - constant, dateUtility for dates operations and logger.
        ├── constants.js
        ├── utility.js
        ├── dateUtility.js
        ├── logger.js
    ├── /configs                        - Use it if need to have some config JSON files as backup or sample like - sample-env.json, iam-roles-policy.json etc.
        ├── iam-role.json
    ├── /mock                           - Contains mock data JSON files
        ├── listUser.json
    ├── /controllers                    - This folder holds the main business logic for the application, it have different files/folders for each modules.
            ├── users.js                    - CRUD APIs for user management like - create user, update and get user(s) detail
            ├── products.js
            ├── orders.js
    ├── /validators                     - This folder is used to contain the API validator files using Joi Validator to validate each API's body, query and path params.
        ├── user.js
        ├── product.js
    ├── /database                       - Contains the separate folders for the databases by their type MySQL, MongoDB, DynamoDB etc. So, that these will be separate according their purpose.
        ├── /mysql                      - This folder contains the files specific for MySQL database.
            ├── /seeders                - This folder contains the SQL files to fill the initial or config data in database.
                ├── products.sql            - This is a SQL file that have INSERT Queries to insert data in database.
            ├── /models                 - This folder is for Sequelize ORM models defined for each MySQL table, files name are according MySQL table names.
                ├── user.js
                ├── index.js
            ├── /migrations             - This folder can use to have the SQL scripts for database schema or data migrations like - to create database, tables and to add, rename columns, & to add or drop table and indexes etc.
            ├── queries.js              - This file have all the RAW MYSQL complex queries.
            ├── schema.ddl.sql             - This SQL file have complete DDL schema of the database.
        ├── mongoDB                     - This folder contains the files specific for MongoDB database.
            ├── /models                 - Use to store files for MongoDB collection models these can be via Mongoose ORM or MongoDB itself.
    ├── /es                             - This folder is for ElasticSearch related operations
        ├── /mapping                    - Index mapping JSON files.
            ├── /product.json               - File to store the mapping of product index.
        ├── index.js                    - This file use to export the re-usable methods from the other files in-side the /es folder.
        ├── reader.js                   - This has methods for ES Search Queries.
        ├── writer.js                   - This has methods for ES Insert, Update, Delete Queries.
    ├── /jobs                           - This folder contains the batch & schedule jobs
    ├── /resources                      - This folder is for containing yml files.
    ├── /routes                         - This folder contains the APIs routes for NodeJS.
        ├── routes.js                   - This is the main route file that has the routes & handlers mapping in our own custom format without any 3rd party library like - {'GET /ap1/users': 'UsersController:getAll'}
        ├── fastifyRoutesLayer.js          - This is like a middleware that reads the routes-mapping from the "routes.js" file and prepare & setup the Fastify routes instance.
        ├── expressRoutesLayer.js          - This is like a middleware that reads the routes-mapping from the "routes.js" file and prepare & setup the ExpressJS routes instance.
    ├── /scripts                        - This folder holds all the scripts required for the project like - for APIs, server & serverless build, deploy & run unit-tests etc.
        ├── /build                          - Folder to contain all the scrips to prepare server build.
        ├── /deploy                         - Folder to contain all the scrips to deploy the APIs.
    ├── /webpack                        - The folder holds the webpack=config files, to create minify & uglify build for the NodeJS. It can have more than one files as per requirement.
    ├── serverless.js                   - This is the main API handler of all APIs for the AWS Lambda or stateless environment APIs.
    ├── server.js                       - This is the handler for server environment APIs.
    ├── package.json                    - NPM package JSON file.
    ├── package-lock.json               - NPM package-lock SON file.
    ├── sample.env                      - Environment file to store the key-value pair data that can be access using "process.env".
```
