## Installation

### GitHub repository setup

1. Create new repository from `@mern-monorepo-starter` template [here](https://github.com/new?template_name=monorepo-mern-railway-starter&template_owner=brunotot).

2. Navigate to **Repo > Settings > Actions - General** and save the following Workflow-related options:

   1. `Read and write permissions` checked
   2. `Allow GitHub Actions to create and approve pull requests` checked

3. Now GitHub actions are ready for usage. Let's now re-run the autogenerated TypeDoc workflow so it generates the `gh-pages` branch. Navigate to **Repo > Actions > MERN Sample App - TypeDoc** and click on **Run workflow**

4. After the `gh-pages` branch is generated, navigate to **Repo > Settings > Pages** and save the `gh-pages` branch as the deployment branch.

5. That's it! Now your GitHub repository is ready to be used for deployment

### Local installation

1. Clone the previously created repository to your local machine

   ```sh
   git clone https://github.com/REPO_USER/REPO_NAME.git
   ```

2. Change directory to the cloned one from Step **#1**

   ```sh
   cd REPO_NAME
   ```

3. Install local packages and run prepare scripts

   ```sh
   pnpm install
   ```

4. That's it! Now you may open the project in **VSCode**
   ```sh
   code .
   ```

### Railway setup

1. Create an account on Railway [here](https://railway.app/login)

2. Install `@railway/cli` if you don't have it already

   ```sh
   npm i -g @railway/cli
   ```

3. Now you have access to the **railway** command. See [Railway CLI documentation](https://docs.railway.app/reference/cli-api)

   ```sh
   railway --help
   ```

4. Login to Railway CLI

   ```sh
   railway login
   ```

5. Create a new Railway project

   ```sh
   railway init
   ```

6. Setup created project through Railway's website (the link will be printed to the console)
   <!--   > [!WARNING]
      > To gain access to Railway Deployments you should upgrade your Railway account to at least a Hobby tier ($5.00 / month). -->

   - setup **MongoDB** service
     1. create MongoDB service by clicking on **New > Database > Add MongoDB**
     2. under **MongoDB Service > Data** create `test` database
     3. under **MongoDB Service > Data** create `production` database
     4. under **MongoDB Service > Data** create `development` database
     5. under **MongoDB Service > Variables** section, find and store the value of `MONGO_URL` locally
   - setup **Backend** service - **Express app**

     > [!WARNING]
     > Incoming steps require at least a `Hobby` plan on the Railway account (lowest priced at $5/month)

     1. create Backend service by clicking on **New > GitHub Repo**
     2. connect your repository to your Railway project
     3. edit service name to `Backend`

   - setup **Frontend** service - **React app**