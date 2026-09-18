# React Challenges Starter Template

A starter template for doing [the React Challenges](https://courses.cs.northwestern.edu/394/guides/react-challenges.html). This template includes React, TypeScript, Vite, and Vitest for testing, as well as CoPilot instructions. There are a few files for the initial coding tasks the `docs` folder.

# Requirements

Node 24 or greater is assumed.

## Setting up your local copy

To create a new repository for doing the challenges, run the following commands in your terminal, replacing `your-app-name` with the name of your app.

```
cd your-projects-folder
npx gitpick criesbeck/react-start your-app-name
cd your-app-name
npm install
git init
git add .
git commit -m "Initial commit"
```

The above steps will create a clean local copy of the starter template. You can then [put it on GitHub](https://docs.github.com/en/get-started/importing-your-projects-to-github/importing-source-code-to-github/adding-locally-hosted-code-to-github#adding-a-local-repository-to-github-using-git).

## Specific instructions for doing the challenges

One step in the React Challenges is to create a learning report for each task. One item in the report is your specification for what should be built. Put your specifications in markdown files in the `docs` folder. A possible specification for the first task is in `docs/show-courses.md`. It shows how to include a screenshot of the expected output. You can use this as a template for your own specifications. 

Then in VS Code, tell CoPilot to "Write code to implement the specification in docs/show-courses.md". This way you will have a history of your initial specifications for later review. You can also use the `docs` folder to keep any other design notes.
 
## Scripts

**package.json** defines the following standard Vite scripts:

| Script           | Description                                         |
| -----------------| --------------------------------------------------- |
| npm run dev      | Runs the app in the development mode.               |
| npm run build    | Builds the app for production to the `dist` folder. |
| npm run serve    | Serves the production build from the `dist` folder. |
| npm test         | Starts a Jest-like test loop                        |
| npm run coverage | Runs the tests, displays code coverage results      |


## Folder Structure

```
your-app-name
|-- .github
|   └── copilot-instructions.md
|-- docs
|   └── show-courses.md
|   └── text-ui.png
|   └── card-ui.pngho
├── public
│   └── robots.txt
│   ├── vite.svg
└── src
    ├── index.css
    ├── main.tsx
    ├── vite-env.d.ts
├── .gitignore
├── eslint.config.js
├── index.html
├── package.json
├── README.md
├── tsconfig.app.json
├── tsconfig.son
├── tsconfig.node.json
├── vite.config.ts
```

## Credits

Inspired by [SafdarJamal/vite-template-react](https://github.com/SafdarJamal/vite-template-react).
Expanded to include Vitest and some sample tests.

Thanks to Neeraj Dalal for [gitpick](https://github.com/nrjdalal/gitpick).

Gitignore file created with [the Toptal tool](https://www.toptal.com/developers/gitignore/api/react,firebase,visualstudiocode,macos,windows).


## License

This project is licensed under the terms of the [MIT license](./LICENSE).
