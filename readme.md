# Media Cleaner

Media Cleaner is a simple CLI tool to clean up your media library based on your Overseerr requests and Tautulli history, written in Rust.

It was written to help me clean up my Plex library, but it should work for anyone with a similar setup. It's not perfect, but it works for me. (This project was written partly to help me learn Rust, so please don't judge me too harshly, though feedback is always welcome.)

## Installation

Just download the latest release for your platform from the [releases page](https://github.com/Supergamer1337/media-cleaner/releases).

## Usage

Make sure you have a config file in the same directory as the executable (or more specifically the root of the working directory when you launch it). It should be named `config.yaml` and look something like this (this was chosen instead of CLI arguments to make it easier for repeated use):

```yaml
items_shown: 5 # The number of items to show in the list of items to select. Useful to limit if your terminal is small, as it can be quite buggy if the list doesn't fit.
overseerr:
    url: https://YOUR_OVERSEERR_URL
    api_key: YOUR_API_KEY
tautulli:
    url: https://YOUR_TAUTULLI_URL
    api_key: YOUR_API_KEY
tmdb:
    v3_key: YOUR_API_KEY
sonarr:
    url: https://YOUR_SONARR_URL
    api_key: YOUR_API_KEY
radarr:
    url: https://YOUR_RADARR_URL
    api_key: YOUR_API_KEY
```

You can get your api keys from the respective applications. A simple search should help you find it.

Once you have your config file, you can run the program with `./media-cleaner` (or `.\media-cleaner.exe` on Windows). If nothing is shown immediately, you have to wait for it to finish all the requests to gather the appropriate data. Afterwards it will bring up a list of all your requests, with the media data associated with that item (watch history, space, etc.), simply select the ones you want to remove (with space) and press enter. This will (after a confirmations screen) remove the request from Overseerr and tell Sonarr and Radarr to remove the show and its files.

## Issues and PRs

You are welcome to open issues, but please be aware that this is a hobby project written to help me learn Rust, and as such have no ambitions to a) implement features I don't want (though you are free to open a PR and I'll have a look at it), and b) fix issues that don't plague me personally (unless I feel it is large enough to warrant a fix).

When it comes to PRs, I'm happy to accept them, but please be aware that I'm not a professional programmer (yet), so I might not be able to give you the best feedback. Similarly, it may take some time while I take the time to look at it.

## License

This project is licensed under the MIT license. See the [LICENSE](LICENSE) file for more details.
