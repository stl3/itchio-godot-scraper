# itch.io Godot Scraper

[![GitHub license](https://img.shields.io/github/license/hiulit/itchio-godot-scraper?style=flat-square)](https://github.com/hiulit/itchio-godot-scraper/blob/master/LICENSE)

A scraper for Godot games hosted on https://itch.io/.

![itch.io Godot scraper banner](itchio-godot-scraper-banner.jpg)

## 🌐 API URL

https://itchio-godot-scraper.vercel.app/api

Auto updated every day at 12:00 CET.

## 🚀 Usage

- `/api` - Get all the games.
- `/api/games` - Get all the games titles.
- `/api/game/title/:title` - Get game by title.
- `/api/game/id/:id` - Get game by id.
- `/api/authors` - Get all the authors.
- `/api/authors/top/:number` - Get top authors by game count.
- `/api/author/:author` - Get games by author.
- `/api/platforms` - Get all the platforms.
- `/api/platforms/:platform` - Get games by platform.

## 🤔 How does the scraper finds games

To find a specific game, the scraper uses `/api/game/title/:title`.

What the scrapes does is take `:title` parameter and split it in words, following some conventions (see below). Then it looks for all the games that have those words in it, and returns the one that have the more words.

For the scraper to be able find the game, the game's title (and particularly the game's build name) needs to follow any of these conventions:

- It must be camelCase (e.g. `thisIsMyGame`).
- It must use dashes or underscores (e.g. `this-is-my-game` or `this_is_my_game`).
- It must use spaces (e.g `this is my game`).
- It must use dots (e.g. `this.is.my.game`).

## ℹ️ Troubleshooting

### The scraper can't find a game

For the scraper to be able to find a game, the game's build name must follow these conventions:

- It must have the game's title in it (it may seem obvious but some game builds doesn't match with the game's title at all).
- It must follow any of the conventions above.

## 🛠️ Development

### Prerequisites

* [Git](https://git-scm.com/) installed on your computer.
* [Node.js](https://nodejs.org/en/) installed on your computer.

**Warning:** Don't update the `node-fetch` package.

### Installation

```bash
# Clone the repository.
git clone https://github.com/hiulit/itchio-godot-scraper.git
# Go to the repository folder.
cd itchio-godot-scraper
# Create a temporary folder, needed for some files.
mkdir .tmp
# Install the node modules.
npm install
```

### Usage

* Run `npm start` to start the production environment.  
This will use the data from https://raw.githubusercontent.com/hiulit/itchio-scraper/master/all.json.
* Run `npm run dev` to start the development environment.  
This will use the local `all.json` generated by the `update-games.js` script.  
Use this environment to develop/test new features.
* Run `npm run update-games` to scrape all the Godot games from https://itch.io and store them in `all.json`.

## 👤 Author

**hiulit**

- Twitter: [@hiulit](https://twitter.com/hiulit)
- GitHub: [@hiulit](https://github.com/hiulit)

## 🤝 Contributing

Feel free to:

- [Open an issue](https://github.com/hiulit/itchio-godot-scraper/issues) if you find a bug.
- [Create a pull request](https://github.com/hiulit/itchio-godot-scraper/pulls) if you have a new cool feature to add to the project.
- [Start a new discussion](https://github.com/hiulit/itchio-godot-scraper/discussions) about a feature request.

## 🙌 Supporting this project

If you love this project or find it helpful, please consider supporting it through any size donations to help make it better ❤️.

[![Become a patron](https://img.shields.io/badge/Become_a_patron-ff424d?logo=Patreon&style=for-the-badge&logoColor=white)](https://www.patreon.com/hiulit)

[![Suppor me on Ko-Fi](https://img.shields.io/badge/Support_me_on_Ko--fi-F16061?logo=Ko-fi&style=for-the-badge&logoColor=white)](https://ko-fi.com/F2F7136ND)

[![Buy me a coffee](https://img.shields.io/badge/Buy_me_a_coffee-FFDD00?logo=buy-me-a-coffee&style=for-the-badge&logoColor=black)](https://www.buymeacoffee.com/hiulit)

[![Donate Paypal](https://img.shields.io/badge/PayPal-00457C?logo=PayPal&style=for-the-badge&label=Donate)](https://www.paypal.com/paypalme/hiulit)

If you can't, consider sharing it with the world...

[![Share on Twitter](https://img.shields.io/badge/Share_on_Twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/intent/tweet?url=https%3A%2F%2Fgithub.com%2Fhiulit%2Fitchio-godot-scraper&text="itch.io+Godot+Scraper"%3A%0D%0AA+scraper+for+%23GodotEngine+games+hosted+on+%40itchio.%0Aby+%40hiulit%0A)

... or giving it a [star ⭐️](https://github.com/hiulit/itchio-godot-scraper/stargazers).

Thank you very much!

## 👏 Credits

Thanks to:

- **Andrea Calabró** - For creating the "Godot logo".
- [OpenMoji](https://openmoji.org/) (the open-source emoji and icon project
) - For the "magnifying glass" and "spider" emojis.
- [itch.io](https://itch.io/press-kit) - For the "itch" logo.

## 📝 Licenses

- Source code: [MIT License](LICENSE).
- Godot logo: [CC BY](https://creativecommons.org/licenses/by/4.0/).
- All emojis: [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0).
