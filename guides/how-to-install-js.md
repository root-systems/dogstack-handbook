# How to install Node.js

Are you ready to install [Node.js](https://nodejs.org)? Great! ＼(＾▽＾)／

We're going to use [nvm (Node Version Manager)](https://github.com/creationix/nvm)) to make this easy and awesome.

## 1. Install `nvm`

To install or update `nvm`, you can use the [install script][https://github.com/creationix/nvm/blob/v0.23.3/install.sh] using cURL:

```sh
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.1/install.sh | bash
```

or Wget:

```sh
wget -qO- https://raw.githubusercontent.com/creationix/nvm/v0.33.1/install.sh | bash
```

<sub>The script clones the `nvm` repository to `~/.nvm` and adds the source line to your profile (`~/.bash_profile`, `~/.zshrc`, `~/.profile`, or `~/.bashrc`).</sub>

For more help or instructions, see the [`nvm` README](https://github.com/creationix/nvm/blob/master/README.markdown).

## 2. Install `node` and `npm`

Once we have `nvm` installed, we can use it to install the [long-term stable](https://github.com/nodejs/LTS) version of Node.js.

```sh
nvm install lts
nvm use lts
nvm alias default lts
```

You should now be able to run `node` (a Node JavaScript interpreter) or `npm` (the Node Package Manager).

For best results, let's upgrade `npm` to the latest version.

```sh
npm install -g npm@latest
```

Now we're ready to go, welcome to the wild world of Node.js, let the festivities begin!

(((o(*ﾟ▽ﾟ*)o)))
