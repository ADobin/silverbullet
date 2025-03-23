# Introduction
SilverBullet is an open source **personal productivity platform** built on [[Markdown]], turbo charged with the scripting power of [[Space Lua|Lua]]. You [[Install|self host]] it on your server, access it via any modern browser on any device (desktop, laptop, mobile). Since SilverBullet is built as a [[Local First]] [[PWA]], it is fully offline capable. Temporarily don’t have network access? No problem, SilverBullet will sync your content when you get back online.

In case you were wondering: yes, you are looking at a (read-only) instance of SilverBullet right now. Switch off your Internet connection, and this website will still be available for your reading pleasure.

# A Typical Journey
You may start your SilverBullet journey by simply thinking of it as a nice _note taking app_.

Because, well, it is.

You write notes in [[Markdown]] and get [[Live Preview]]. It feels WYSIWYG while still easily accessing the markdown that lies underneath. There are convenient keyboard shortcuts to make your text **bold** or _italic_. You can create [[Links]] to other pages, via the `[[other page]]` syntax. As you navigate your [[Spaces|Space]] (that’s what we call a SilverBullet instance) by clicking these links, you will see [[Linked Mentions]] to get a feel of how your pages are inter-linked.

That’s nice, but oh my. We’re just getting started.

Then you learn that in SilverBullet, you can embed [[Space Lua]] (SilverBullet’s [[Lua]] dialect) in your pages directly using the `${Lua expression}` syntax. You try something simple, like ${10 + 2} (Alt-click to see the underlying code). You realize you’ll never have to use a calculator again.

But it doesn’t stop there. As it turns out, there are a few [[Lua Widgets]] already implemented that allow you to e.g. create buttons in your pages as well: ${widgets.button("Click me", function() 
  editor.flashNotification "Hello world!"
end)}.

You thought that [[Markdown]] would be a limiting factor to what you can do. But _this_ is opening up a whole new world.

“What’s next,” you wonder, “can I define my _own_ widgets? Nah, that would be too crazy...”

Hold my 🍺.

```space-lua
function scroller(text)
  return widget.new {
    html = "<marquee>" .. text .. "</marquee>"
  }
end
```

Let’s see...
${scroller "Weeeeeeeeee!"}

Ok, that’s cool, but you are serious people. You have work to do. You were promised a productivity platform, so let’s get to it. As exercise material, [[Person/Zef|here’s a page on SilverBullet’s author]] with some [[Frontmatter]] attached.

Let’s see if we can query that somehow:

${query[[
  from index.tag "person"
  select {firstName=firstName, lastName=lastName}
]]}

Noice.

But let’s render this in a slightly more customized way:

${template.each(query[[from index.tag "person"]], template.new[==[
    * [[${ref}]]: **First name:** ${firstName}, **Last name:** ${lastName}, **Location:** ${location}
]==])}

Now we’re talking!

You may have been told there is _no such thing_ as a [silver bullet](https://en.wikipedia.org/wiki/Silver_bullet).

You were told wrong.

# Features
* SilverBullet is a **web application** and therefore instantly accessible wherever a (modern) web browser is available, without the need to install a 200mb Electron app, nor unreliable or proprietary sync setups.
* SilverBullet is a [[Local First]] [[PWA]] keeping a copy of the content in your browser’s local ([IndexedDB](https://developer.mozilla.org/en-US/docs/Web/API/IndexedDB_API)) database, syncing back to the server when a network connection is available.
* **Self-hosted**: _you own your data_. Your [[Spaces|space]] is stored as plain files in a folder on disk on your server. Back it up, sync, edit, publish, script it with any additional tools you like.
* SilverBullet provides an enjoyable [[Markdown]] writing experience with a clean UI, rendering text using [[Live Preview|live preview]], further **reducing visual noise** while still providing direct access to the underlying markdown syntax.
* SilverBullet supports wiki-style **page linking** using the `[[page link]]` syntax. Incoming links are indexed and appear as [[Linked Mentions]] at the bottom of the pages linked to, thereby providing _bi-directional linking_.
* SilverBullet is optimized for **keyboard-based operation**:
  * Quickly navigate between pages using the **page switcher** (triggered with `Cmd-k` on Mac or `Ctrl-k` on Linux and Windows).
  * Run commands via their keyboard shortcuts or the **command palette** (triggered with `Cmd-/` or `Ctrl-/` on Linux and Windows).
  * Use [[Slash Commands]] to perform common text editing operations.
* SilverBullet is a platform for [[End-User Programming]] through its support for [[Objects]] and [[Space Lua]].
* SilverBullet can be extended using [[Space Lua]] and [[Plugs]].
* SilverBullet is free, [**open source**, MIT licensed](https://github.com/silverbulletmd/silverbullet) software.

# Install SilverBullet
Convinced to install this yourself? Please proceed to [[Install]], and enjoy!

# What next?
* [[Manual]]: how to use this thing.
* [[CHANGELOG]]: we’re in active development, so things change rapidly. Watch this page to keep up.
* [Roadmap](https://github.com/orgs/silverbulletmd/projects/2/views/1): currently planned features and priorities.
* [Community](https://community.silverbullet.md): join our community: ask questions, share your experiences.
* [Issues](https://github.com/silverbulletmd/silverbullet/issues): if you have ideas or find bugs, please report them.
* [Mastodon](https://fosstodon.org/@silverbulletmd): follow SilverBullet development on [Mastodon](https://joinmastodon.org/).

# Support
If you (hypothetically) find bugs or have feature requests, post them in [our issue tracker](https://github.com/silverbulletmd/silverbullet/issues). Want to contribute? [Check out the code](https://github.com/silverbulletmd/silverbullet).

And... join our [community](https://community.silverbullet.md/)!