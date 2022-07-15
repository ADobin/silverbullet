# Silver Bullet
## Markdown as a platform
Silver Bullet (SB) is highly-extensible, [open source](https://github.com/silverbulletmd/silverbullet) **personal knowledge management** software. Indeed, that’s fancy language for “a note taking app with links.”

At its core, SB is a Markdown editor that stores _pages_ (notes) as plain markdown files in a folder referred to as a _space_. Pages can be cross-linked using the `[[link to other page]]` syntax. However, once you leverage its various extensions (called _plugs_) it can feel more like a _knowledge playground_, allowing you to annotate, combine and query your accumulated knowledge in creative ways, specific to you. To get a good feel for it, [watch this video](https://youtu.be/RYdc3UF9gok).

Cool, no?

What does Silver Bullet look like? Well, have a look around. **You’re looking at it at this very moment!** 🤯

Note that what you’re looking at is not a fully functional version, because the _back-end is read-only_. That said, it should give you some feel for what it’s like to use SB before making the commitment of running a single `npx` command (see below) to download and run it locally in its fully functioning mode.

So, feel free to make some edits in this space. Don’t worry, you won’t break anything, nothing is saved (just reload the page to see).

Here are some things to try:

* Click on the page name at the top, or hit `Cmd-k` (Mac) or `Ctrl-k` (Linux and Windows) to open the **page switcher**. Type the a name of a non-existing page to create it (although it won’t save in this environment).
* Click on the run button (top right) or hit `Cmd-/` (Mac) or `Ctrl-/` (Linux and Windows) to open the **command palette** (note not all command will work in this quasi read-only mode).
* Select some text and hit `Alt-m` to highlight it, or `Cmd-b` (Mac) or `Ctrl-b` to make it bold.
* Click a link somewhere in this page, to navigate there.
* Start typing `[[` somewhere to insert a page link (with completion).
* [ ] Tap this box 👈 to mark this task as done.
* Start typing `:party` to trigger the emoji picker 🎉
* Type `/` somewhere in the text to invoke a **slash command**.
* Open this site on your phone or tablet and… it just works! 

## Explore more
Click on the links below to explore various aspects of Silver Bullet more in-depth:

[[🤯 Features]]
[[💡 Inspiration]]
[[🔌 Plugs]]
[[🔨 Development]]
[[🗺 Roadmap]]

More of a video person? Here’s two to get you started:

* [A Tour of Silver Bullet’s features](https://youtu.be/RYdc3UF9gok) — spoiler alert: it’s cool.
* [A look the SilverBullet architecture](https://youtu.be/mXCGau05p5o) — spoiler alert: it’s plugs all the way down.

## Principles
Some core principles that underly Silver Bullet’s philosophy:

* **The truth is in the markdown.** Markdown is simply text files, stored on disk. Nothing fancy. No proprietary formats or lock in. While SB uses a database for indexing and caching some data, all of that can be rebuilt from its markdown source at any time.
* **What you see is what it is.** No magic or hidden content.
* **Single mode.** SB doesn’t have a separate view and edit mode. You’re always in edit mode, and you like it that way.
* **Extend it your way**. SB is highly extensible, and you can customize it your liking and your workflows.

## Running Silver Bullet
Do you like what you’re seeing? Are you ready to take that next step? Install it yourself locally or on your server! It’s free.

To run a release version, you need to have a recent version of [node.js installed](https://nodejs.org/en/) (16+). Silver Bullet has only been tested on MacOS and Linux thus far. It could also run on Windows, let me know if it does.

To install and run SB, create a folder for your pages (can be empty or an existing folder with `.md` files) and run the following command in your terminal:

    npx @silverbullet/server <path-to-folder>

Optionally you can use the `—port` argument to specify a HTTP port (defaults to `3000`) and you can pass a `—password` flag to require a password to access. Note this is a rather weak security mechanism, so it’s recommended to add additional layers of security on top of this if you run this on a public server somewhere (at least add TLS). Personally I run it on a tiny Linux VM on my server at home, and use a VPN (Tailscale) to access it from outside my home.

That’s it! Enjoy.

If you (hypothetically) find bugs or have feature requests, post them in [our issue tracker](https://github.com/silverbulletmd/silverbullet). Want to contribute? [Check out the code](https://github.com/silverbulletmd/silverbullet).