---
title: On Site / Premises Deployment  Steps
layout: template
filename: on-site-steps
---

# On Site / Premises

---

## Install Node JS
- Download and install Node JS using the link provided
[Download Link](https://nodejs.org/dist/v14.17.1/node-v14.17.1-x64.msi)

- Start CMD with administrator privileges.
- Globally installed PM2:

```bash
npm install -g yarn
```

## Install MxB TV Dependencies

- Go to the parent folder of the MxB TV project.
- Start CMD with administrator privileges.
- Then run the command below to install the project dependencies.

```bash
yarn
```

## Install PM2
- Start CMD with administrator privileges.
- Globally installed PM2:

```bash
 npm i pm2 -g
```

Then set up PM2 to boot from start:

- Install and configure:

  ```bash
  npm i -g pm2-windows-service
  ```

- Add system environment variable: PM2_HOME = C: \ users \ *** \. PM2 (specific path can be viewed by PM2 -V)
- Open a new CMD window with administrator privileges, perform the following command to install the service:

  ```bash
  pm2-service-install
  ```

- To start the MxB TV server run the following command in the CMD with administrator privileges, enter the corresponding application directory:

  ```bash
  pm2 start npm --name "You have to get the name" - run start
  ```

  **If your run status is: Online, it means normal.**

## Setup IIS

- Open IIS -> Selected Server Name -> Double-click the Application Request Routing Cache -> clicking on the right function view IIS node -> Click on the server proxy settings -> check box in the *ENABLE PROXY*

- Add MxB TV, directory Select the MxB TV project folder, configure the project domain name

- Then check the Test website, select the URL rewrite, add a rule

```js
Mode: ^ (. *)
Condition: {http_host} ^ www.xxxx.com (your domain) $
Rewrite URL: http: //127.0.0.1: 3000 / {R: 1} Your MxB TV configuration of the address and port
```



