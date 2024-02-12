
<img src="https://moodle.wsiz.edu.pl/pluginfile.php/1/theme_alpha/customlogotopbar/1707397324/wsiz-favicon.png" width="75" height="75"></img>  
<br />
I will make docker soon for both repositories
## Requirements
1. Node.js installed
2. Clerk account token (thirdparty platform for authentication)
3. Cloudinary account token (thirdparty platform to store images)
## Getting Started
### Basic set up
First, clone the repository using git or download .zip archive
```
git clone https://github.com/Zacky3181V/admin-panel
```
2. Open the project with whatever tool you have - I prefer VSCode  
3. Run ```npm i``` to install all necessary dependencies


### Database
1. Run ```prisma init``` in the terminal in the root of the project
It will create .env file with DATABASE_URL. Please, read the [documentation](https://www.prisma.io/docs/getting-started/setup-prisma/start-from-scratch/relational-databases/connect-your-database-node-postgresql) of prisma on how to setup a database for local use. I used planetscale as a platform to host my database

2. Put the tokens from Clerk and Cloudinary there like this
```
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=key_here_without_quotes
CLERK_SECRET_KEY=key_here_without_quotes
NEXT_PUBLIC_CLERK_SIGN_IN_URL=/sign-in 
NEXT_PUBLIC_CLERK_SIGN_UP_URL=/sign-up 
NEXT_PUBLIC_CLERK_AFTER_SIGN_IN_URL=/
NEXT_PUBLIC_CLERK_AFTER_SIGN_UP_URL=/
NEXT_PUBLIC_CLOUDINARY_CLOUD_NAME="put-name-here"
```

4. In the terminal write following commands, it will create a database in the connection string you provided in DATABASE_URL  
```
npx prisma generate
npx prisma db push
```

### Running
Start the project by typing following commands in the terminal
```bash
npm run dev
# or
yarn dev
# or
pnpm dev
# or
bun dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

## Token for Store
1. If everything is fine project should launch with no errors. Youy will see clerk authentication window and after that you must create first store then you will be redirected to dashboard page. Please go to **Settings** tab and find the token you will need it when setting up the [Store](https://github.com/Zacky3181V/store) project

