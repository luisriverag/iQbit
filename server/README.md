# iQbit Standalone Server

So you want to be cool and run this all on its own huh

## Got some Node?

Alright, first thing we'll need is NodeJS.
https://nodejs.org/en/download/

Run `node -v` to double check. Any version at least somewhat recent should do. Maybe >12 ? idk

## Get it to run

I made it so you can run everything in the root repository once you have node running.

Remember, all these will happen in the ROOT DIRECTORY of this repo.

#### 1. Run `npm run server-setup`

This will copy the `.env.default` into a `.env` file and install all dependencies for this to work.

**Windows Users:** This command uses unix commands to copy the `.env.default` into a `.env` file. If you're on Windows I
suggest manually copying the `.env.default` in the `/server` directory and renaming it to `.env`. Then again in
the `/server` directory, run `npm install` to install the dependencies.

#### 2. Run `npm run server-start`

This will, well, start the server. Additionally it will restart the server (or attempt to) if anything goes wrong.

### 3. Go to `http://localhost:8081` and try to login

If you changed the port in the .env file the port on the url above will be different obviously

### More things to know

### Stopppppp It

You can also run `npm run server-stop` from the root directory to stop the server

### Configuration

I made it so you can change the qBittorrent host server pointer and the port where iQbit will run in the .env file.

Remember,the only file being actually used by the server is `.env`!! `.env.default` is just a setup file.

The env variables look like this

    QBIT_HOST=http://localhost:8080
    STANDALONE_SERVER_PORT=8081

Which makes some assumptions, mainly assuming that you're running this in the same computer you're running qbittorrent.
Which isn't necessary. Since we're proxying requests, you can target a completely different IP for the host.

STANDALONE_SERVER_PORT is the port that the app will use to display iQbit. 