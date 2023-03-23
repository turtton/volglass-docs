[Github](https://github.com/turtton/volglass)
volglass is a fork project of [MindStone](https://github.com/TuanManhCao/digital-garden), a project that aims to be an alternative to ObsidianPublish.

## Setup your content

### Using volglass-cli(Recommended)

#### Requirements
- NodeJS(v17 or above)
- Npm(v8 or above)

#### Setup volglass-cli
Be sure to follow these steps because volglass-cli requires an npm project (`package.json`).

```sh	
npm init --yes
npm install --save-dev volglass-cli
npx volglass init
```

Now, volglass-cli installs `pnpm` and creates `posts` directory.
The `posts` directory is used to store the content in the obsidian vault. It is recommended that you create a README.md in the posts directory (this will be your first page in website).

The next step can be chosen from the following two options, depending on your objectives.

**1.Run on your local machine**
-  `npx volglass serve`
Volglass-cli downloads the latest volglass project and serve content automatically.

Open this link in your browser http://localhost:3000/ 

**2.Build as static site contents**
- `npx volglass build`
This task outputs content to `_volglass` directory.

> If you want to build as node.js server, add `-n` flag in command.

### Setup manually
Although not recommended, you can also build with Docker in this case.

#### Requirements
- NodeJS(v17 or above)
- Pnpm(v7)

#### Clone volglass
- `git clone https://github.com/turtton/volglass.git`(or `git@github.com:turtton/volglass.git`)
Place markdown files in the posts directory and image files in the public/images directory. Do not separate the image files into directory hierarchies.

#### Build your contents
- `pnpm run build && pnpm run export`
next.js outputs content in `out` directory.

#### Build docker iamge(optional)
Thanks to [ilkersigirci](https://github.com/turtton/volglass/pull/2) you can build docker image.
- `docker build -t local/volglass:latest && docker run -d -p 3000:3000 --name volglass local/volglass:latest`