# Real World Nuxt

> Real World Nuxt applications and their open source codebases for developers to learn from

This project brings together active, open source Nuxt apps in one repository, making it easier for developers to download the collected codebases and learn from Nuxt apps written by experienced developers. Reading open source code can be an invaluable learning aid. You'll find the source code in the [`apps/`](apps/) subdirectory.

Real World Nuxt helps developers:

- Find example usage of Nuxt features and composables you're unsure of
- Learn how other developers structure their Nuxt applications
- Discover how to use Nuxt modules and plugins
- See real-world implementations of Nuxt 3 patterns
- Explore different approaches to API integration, state management, and more
- Leverage LLMs to analyze patterns across multiple codebases

## How to install on your computer

Ensure you have git installed: https://git-scm.com

```bash
# Clone this git repo:
git clone git@github.com:yourusername/real-world-nuxt.git

cd real-world-nuxt/

# The Nuxt apps are linked to as git submodules.
git submodule update --init --single-branch --jobs 4

echo "All done! You can now explore the apps/ directory."
```

## How to update your local copy of real-world-nuxt

Pull the latest commits from this repo and update submodules:
```bash
git pull
git submodule update --remote
```

## Other Real World Codebase Collections

- Real World Rails https://github.com/eliotsykes/real-world-rails
- Real World Sinatra https://github.com/jeromedalbert/real-world-sinatra
- Real World React https://github.com/jeromedalbert/real-world-react
- Real World Ruby Apps https://github.com/jeromedalbert/real-world-ruby-apps
- Real World Django https://github.com/ckrybus/real-world-django
- Real World Ember https://github.com/eliotsykes/real-world-ember

## How you can analyze Real World Nuxt apps

#### Find all composables

Use grep/ripgrep to find composable patterns:

```bash
# Find all composables using useAsyncData
rg "useAsyncData" apps/ -A 3

# Find useState usage
rg "useState" apps/ -A 3
```

#### Find all page components

```bash
# List all pages directories
find apps/ -type d -name "pages"

# Find all dynamic routes
find apps/ -name "\[*.vue\]"
```

#### Analyze component patterns

```bash
# Find all components
find apps/ -path "*/components/*.vue"

# Find composables
find apps/ -path "*/composables/*.ts" -o -path "*/composables/*.js"
```

#### Find projects using specific Nuxt modules

```bash
# Find all projects using a specific module (e.g., @nuxt/content)
find apps/ -name "nuxt.config.ts" -o -name "nuxt.config.js" | xargs grep "@nuxt/content"

# Find all package.json files and search for a module
find apps/ -name "package.json" | xargs grep "nuxt-module-name"
```

#### Explore API patterns

```bash
# Find server API routes
find apps/ -path "*/server/api/*.ts" -o -path "*/server/api/*.js"

# Find middleware
find apps/ -path "*/middleware/*.ts" -o -path "*/middleware/*.js"
```

#### Use LLMs for deeper analysis

With all the codebases in one place, you can:
- Point an LLM (like Claude, GPT-4, etc.) at the entire directory
- Ask questions like "Show me how these apps implement authentication"
- Find patterns across multiple real-world implementations
- Discover best practices by seeing what experienced developers do

## Information for Contributors

#### How to add a Real World Nuxt app

Given a GitHub repo for a Nuxt app `githubuser/foo`:

```bash
# Inside real-world-nuxt root:
# Replace <DEFAULT_BRANCH> with correct branch (probably 'main' or 'master').
git submodule add -b <DEFAULT_BRANCH> git@github.com:githubuser/foo.git apps/foo
```

#### Criteria for adding apps

Apps should:
- Be open source and publicly available
- Use Nuxt 2 or Nuxt 3
- Be actively maintained or represent quality code
- Be real-world applications (not just demos or tutorials)
- Have meaningful code to learn from

#### How to remove a git submodule

Only use this if a previously public repo has been removed:

```bash
# Remove the submodule from .git/config
git submodule deinit -f path/to/submodule

# Remove the submodule from .git/modules
rm -rf .git/modules/path/to/submodule

# Remove from .gitmodules and remove the submodule directory
git rm -f path/to/submodule
```

## Contributing

Contributions are welcome! If you know of a great open source Nuxt application, please:

1. Check it meets the criteria above
2. Add it as a submodule
3. Submit a pull request

## License

This repository structure and documentation is provided as-is. Each application in the `apps/` directory is licensed under its own terms - please check individual repositories for their licenses.

