# wiki
Boilerplate repository to allow access to a web-based flat file wiki while in software-restricted environments (such as workplaces). Uses Featherwiki's Wren 'Ruffled' version for compatibility's sake.

## The Setup

This static page is intended to be used via an external folder of markdown files, and allows rendering and full-text search on devices that otherwise would not allow for software to be installed (such as workplace computers). The current flavour of FeatherWiki in place is the 'ruffled' version of Wren, which should allow the most compatibility in terms of moving the wiki to other hosting solutions (such as [Tiddlyhost](https://tiddlyhost.com/)).

It has the following extensions installed:

- [Upgrade Feather Wiki](https://feather.wiki/?page=extension_upgrade)
- [HTML To Markdown](https://feather.wiki/?page=extensions_html_to_markdown)
- [Marked.js Replacement](https://feather.wiki/?page=extensions_marked-js_replacement)
- [Data Import/Export](https://feather.wiki/?page=extensions_import-export)
- [Full Search](https://feather.wiki/?page=extension_full_search)

It also has the following settings enabled:

- [x] Include your wiki content in simple HTML for non-JS browsers. Nearly doubles output size.

### Why not use (X) solution, though?

Often there are various licensing and policy issues that prevent someone from using their preferred tooling everywhere they can go. For example, if you use something like `org-mode` for a PKMS, it might fall apart if you are unable to use Emacs for whatever reason. Since there are a lot of 'tools-of-the-trade' and tricks used as part of the tech industry however, it's useful to be able to still have access to your PKMS when all you can use is a browser.

I originally had a local TiddlyWiki file for this purpose, but had issues with it sometimes getting deleted when trying to use Git-based saving. I didn't particularly trust it to hold a career's worth of knowledge for me without losing any information. This was primarily why I originally didn't want to use FeatherWiki either, and had originally tried to set up a single-file HTML app to work with a set of flat text/markdown files (I figured I could easily send these over as an e-mail attachment or split set thereof at worst), but issues with the File System Access API rendered that impossible also. A flat-file setup (such as a folder of `.md` files) is generally more salvagable in the event of error or failure.

The setup in this repository is experimental, but I think it might be stable:
- Using FeatherWiki with the Data Import/Export extension allows me to keep a flat file folder, but have a reasonably featured web-application to use.
  - `github.com` shouldn't *theoretically* be blocked in any organization that houses developers, but even if it does, you can run this wiki locally since all the extensions are referred to as local `.js` files.
- A flat file folder helps limit the possibility of data loss shenanigans that might occur in a single-html based file.[^1]
- It's unfortunately not something like MultiMarkdown (and YAML doesn't appear to be supported by Marked.js), but in combination with Pandoc a wiki should be transferrable to a variety of contexts if need be.

### How do I use this?

1. (Please) fork or clone this repository into your own GitHub/GitLab/Codeberg repository and host a pages instance.
2. Access the page through your own repository whenever you want to work on new files.
3. Import your folder of notes through the Data Import functionality.
4. When finished with your notetaking, export the files back out using the Data Export functionality.

Note that parts of the FeatherWiki page might not work based on your workplace's browser policy, and the intent is not to keep data saved in the FeatherWiki (though you could use it that way, why not just download FeatherWiki directly, then?) - if for whatever reason it doesn't work, you'll have to revert back to using `notepad` or whatever best equivalent your environment allows.

### Licensing

Since there are multiple local JS files here, licensing differs between parts and I can't simply include a single `LICENSE` file, so I'll state them separately here.

- Both the main FeatherWiki HTML file and most extensions (**excluding** Marked.js) are [licensed](https://codeberg.org/Alamantus/FeatherWiki/#license-clarification) under the *GNU Affero General Public License.*
- Marked.js itself is [licensed](https://github.com/markedjs/marked/blob/master/LICENSE.md) under the *MIT License*

[^1]: I realise this might have just been an issue of me over-configuring my tiddlywiki instance (plus only saving through a GitLab API key), and FeatherWiki might be better - it's still a risk I would prefer not to take since extracting the 'notes' will be difficult.
