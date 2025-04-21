# Environment-variables

## I learned the distinction between infrastructure environments and environment variables, and how they are used in software development to manage different stages of the application lifecycle. Infrastructure environments refer to the various settings—like development, testing, and production—where applications are built, tested, and deployed, each serving a unique purpose. Environment variables, on the other hand, are dynamic values (e.g., database URLs, usernames, and passwords) that change based on the environment, allowing scripts to adapt without hardcoding. For a FinTech product across two AWS accounts, I explored how to configure these variables for local development (e.g., DB_URL=localhost), testing (DB_URL=testing-db.example.com), and production (DB_URL=production-db.example.com), ensuring safe experimentation, controlled testing, and secure live deployment. This foundational understanding helps in managing cloud infrastructure more effectively using shell scripts.

-
- ![image](https://github.com/user-attachments/assets/72a0997c-5983-42cd-919f-120e15179b40)

-
- ![image](https://github.com/user-attachments/assets/edea23e3-164e-445a-97c6-071dd61843d4)

-
-  ![image](https://github.com/user-attachments/assets/56ce0d51-4beb-43f6-a515-d4ae1370c873)

Understanding Infrastructure Environments and Environment Variables
Infrastructure Environments
In software development, infrastructure environments are distinct settings where applications are built, tested, and deployed. The three primary environments are:

Development: Used for building and initial testing of code. Developers work here to implement features and fix bugs.
Testing: A controlled environment to verify the application's functionality, performance, and stability before going live.
Production: The live environment where the application is deployed and accessible to end-users.

Environment Variables
Environment variables are dynamic values that can be set outside the application code and change based on the environment. They allow the same codebase to adapt to different settings without modification. Common examples include:

Database URLs
Usernames
Passwords

Application in FinTech Project
In the context of a FinTech product deployed across two AWS accounts, environment variables play a crucial role. They are configured differently for each environment to ensure appropriate behavior:

Local Development: Variables are set to use local resources, e.g., DB_URL=localhost, DB_USER=test_user, DB_PASS=test_pass.
Testing: Variables point to testing resources, e.g., DB_URL=testing-db.example.com, DB_USER=testing_user, DB_PASS=testing_pass.
Production: Variables are set for live resources, e.g., DB_URL=production-db.example.com, DB_USER=prod_user, DB_PASS=prod_pass.

Proper management of these variables is critical, especially in production, to maintain security and prevent unauthorized access to sensitive information.
Understanding and properly managing infrastructure environments and environment variables is essential for effective cloud infrastructure management, particularly in complex setups like multi-account AWS deployments.



