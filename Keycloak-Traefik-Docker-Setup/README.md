Follow these instructions to setup and run keycloak in Docker. This setup SHOULD be good for production but comes with absolutely NO WARRANTY neither explicit nor implicit. 
I recommend setting this up in the /opt directory, but it is not necessary, set it up where you will.
Step one: Install Docker see docs here: <a href="https://docs.docker.com/engine/install">Docker Install Docs</a>
Step two: Setup directory structure:
  A). Base install: `mkdir Keycloak && cd Keycloak && mkdir themes && mkdir letsencrypt && mkdir postgresconf && touch .env && touch compose.yaml && cd postgresconf && touch pg_hba.conf && touch postgresql.conf`
  B). OPTIONAL this sets up directories for themes etc. run this from within the main Keycloak dir: `cd themes && mkdir mytheme && cd mytheme && mkdir account admin email login`
    You can create multiple themes (different themes for each realm in keycloak), each theme has 4 sub-themes a login theme which customizes the keycloak login page, an account theme for the account,
    an admin theme, and an email theme. An example file layout inside of each sub theme would be: 
    ____________________________________________________________________________________
      themes/
          └── mytheme/
              ├── admin_account_email_login/
              │   ├── theme.properties
              │   └── resources/
              │       ├── css/
              │       │   └── (CSS files here)
              │       ├── image1.png
              │       ├── image2.png
              │       └── (Additional image files here)
    __________________________________________________________________________________________
    __________________________________________________________________________________________
    You can create teh required directory structure within each | admin, email, account, login, directory via:
    `mkdir resources && touch theme.properties && cd resources && mkdir css && cd css && touch styles.css`
