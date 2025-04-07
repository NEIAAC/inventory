# Keeping things organized 📦🧹

![screenshot](./.github/screenshots/first.png)

This repository contains the configuration files to run a **Snipe-IT** instance with _Docker Compose_, a free and open source IT asset/license management system. It is a great tool to keep track of both material and software assets, as well as licenses and contracts, and can be used to manage the lifecycle of these assets, from acquisition to disposal.

## Requirements 📋

- Docker Compose 2.24.0+

## Usage 🚀

- Clone the repository and open a terminal **inside** it.

- Create a `.env` file based on the `.env.example` file.

- Start the docker compose:

  ```shell
  docker compose up --force-recreate
  ```

- Access Snipe-IT at the port you set in the `.env` file, the initial setup page will be shown on the first run, where an admin account will be created for the initial user. This privilege and every other permission can later be assigned to other users and managed in the respective panel.

## Customization 🎨

The `resources` folder contains most of the files we use to personalize our own instance:

- `favicon.ico` - The icon for the website to be added through the admin panel.

- `custom.css` - CSS to be added through the admin panel that hides certain features we don't need that can't be disabled and improves some styling.

- `default-avatar.jpg` - Image to be set through the admin panel as the default for users without a profile picture.

- `logo.png` - Logo that gets displayed in most of the platform, including sent emails, to be set through the admin panel.

## Notes 📝

- To update any of the docker services simply bump the versions in the `image` fields of the `docker-compose.yaml` file and run the `docker compose up --force-recreate` command to restart them with the new version, data will be persisted through the volumes.

- Always beware of **breaking changes** when editing the version field in the `docker-compose.yaml` file! Look at the update notes of each component to see if there are any migration steps required when upgrading, Snipe-IT usually mentions any required steps in their [release notes](https://github.com/snipe/snipe-it/releases) page.
