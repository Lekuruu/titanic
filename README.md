
<p align="center">
  <img width="500" alt="logo" src="https://raw.githubusercontent.com/Lekuruu/titanic/main/.github/logo/logo_medium.png">
</p>

# Titanic

Titanic is a private server made to be compatible with all osu! stable clients (2008-2024).
The goal of this project was to gain deeper insights into the inner workings of Bancho and how it changed over the years.

You can play on it, by [registering on our website](https://osu.titanic.sh/account/register), and [downloading](https://osu.titanic.sh/download) a client. **Keep in mind that only a smaller range of clients will be available there.**
For more questions, feel free to join our Discord server: https://discord.gg/qupv72e7YH

The main goal of this project was achieved. However, there are still a good amount of features that we want to add, which you can view [here](https://github.com/users/osuTitanic/projects/2).

## Setup

Be aware that this project is typically not recommended for use on your own private server, as it is largely customized for our specific needs and can be challenging to modify. However, you are still welcome to use the project as you see fit.

To set up and use this project, it is advisable to use [Docker](https://www.docker.com/), as it is much simpler in most cases. If you do not feel comfortable using docker, here are some instructions for the [manual setup](https://github.com/osuTitanic/titanic/blob/main/SETUP.md), which is not recommended but still possible to do.

Verify that docker is installed:

```
docker --version
```

Clone this project onto your machine:

```
git clone --recurse-submodules --shallow-submodules https://github.com/osuTitanic/titanic.git
```

Rename the `.example_env` to `.env` and **edit it**.

Start the server:

```
docker compose up -d
```

("-d" argument means detached, meaning that containers will run in background)

To turn off the server, from the titanic root folder, execute:

```
docker compose stop
```

If you experience issues on the first run, you may need to restart your containers:

```
docker compose restart
```

If you changed some files around, and don't see your changes applied, execute:

```
(rebuild)
docker compose build
(apply changes & restart affected containers)
docker compose up -d
```

After the setup is done, you should have a PostgreSQL database instance, which you can access using your database management system of choice.
By default, it contains the user `peppy` with the password `recorderinthesandybridge`.

## Updating

Titanic will get updates from time to time, so it's a good idea to apply them once in a while.

Start by first pulling all pending changes into your root folder:

```
git pull
```

After that update all of your submodules:

```
git submodule update --recursive
```

Finally, rebuild and restart all of your containers:

```
docker compose build
docker compose up -d
```

## Patching the client

You can view the instructions for patching the client [here](https://github.com/osuTitanic/clients/blob/main/PATCHING.md).

## Contributing

You are welcome to make any kinds of suggestions or contributions to this project.
Feel free to contact me if you have any questions.

## Credits

- All [testers](https://osu.titanic.sh/g/8) that somehow found the project through this GitHub repo and decided to register through Discord DMs
- Everyone that donated & contributed to this project (you guys are a big help!)
- [Adachi](https://github.com/kanaarima/) for helping with the Discord bot & developing the pp system
- Beatmap mirrors ([osu.direct](https://osu.direct/), [nerinyan](https://nerinyan.moe/) & [mino](https://catboy.best))

## Screenshots

![sanic](https://raw.githubusercontent.com/osuTitanic/titanic/main/.github/images/screenshot007.jpg)
![cool](https://raw.githubusercontent.com/osuTitanic/titanic/main/.github/images/screenshot008.jpg)
![wow](https://raw.githubusercontent.com/osuTitanic/titanic/main/.github/images/screenshot023.jpg)
![nice](https://raw.githubusercontent.com/osuTitanic/titanic/main/.github/images/screenshot005.jpg)
![multiplayer](https://raw.githubusercontent.com/osuTitanic/titanic/main/.github/images/screenshot006.jpg)
