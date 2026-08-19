## How to setup the project
1. Clone the repository:

   ```bash
   git clone https://github.com/SAIMA111/NITJ_Intranet_Culture.git
   cd NITJ_Intranet_Culture
   ```
2. In the backend, if there is no `TeacherFolders` then create one.
3. In the backend create a `.env` file and add the values for the following:
    - **MONGO_URI**
    - **FRONTEND_BASE_URL:** URL of the frontend.
    - **EMAIL_USER:** The email address of the account that will send the email, in case of the forgot password
    - **EMAIL_APP_PASSWORD:** The password of the account that will send the email, in case of the forgot password. Check out any video of node-mailer to know how to set up the app password
    - **PORT**
    - **JWT_SECRET**
    
4. Create 2 terminals in VS Code.
5. Navigate the project:
    - In the first terminal navigate to the server folder `cd Backend`.
        - Run `npm install` to install the dependencies.
        - Run `npm run dev` to start the server.
    - In the second terminal navigate to the client folder `cd Frontend`.
        - Run `npm install` to install the dependencies.
        - Run `npm run dev` to start the client.

6. In **Frontend:** 
    Configure the postcss.config.js with the following:
    ```javascript
    import tailwindcss from 'tailwindcss'
    import autoprefixer from 'autoprefixer'

    export default {
    plugins: {
        tailwindcss: {},
        autoprefixer: {},
    },
    }
    ```
    Similarly configure tailwind.config.js with the following:
    ```javascript
    /** @type {import('tailwindcss').Config} */
    export default {
    content: [
        "./index.html",
        "./src/**/*.{js,ts,jsx,tsx}",
    ],
    theme: {
        extend: {},
    },
    plugins: [],
    }

    ```
7. In **Backend:**
    Run the following scripts to load the department and `faculty_data.csv` into the MongoDB database:
    ```JSON
    Initial Setup:
    1. npm run init-department    (runs once when setting up system to initialize the departments)
    2. npm run init-faculty       (runs once when setting up system to initialize the faculty data)
    
    Later Updates:
    1. Update faculty_data.csv with new entries
    2. npm run update-faculty  (can be run multiple times safely)
    ```



