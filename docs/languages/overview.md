---
ContentId: AC888642-FBE5-43E5-9DC2-47B197717940
DateApproved: 07/09/2025
MetaDescription: In Visual Studio Code we have support for all common languages including smart code completion and debugging.
---
# Programming Languages

## Hundreds of programming languages supported

In Visual Studio Code, we have support for almost every major programming language. Several ship in the box, for example, JavaScript, TypeScript, CSS, and HTML but more rich language extensions can be found in the [VS Code Marketplace](https://marketplace.visualstudio.com/vscode/Languages).

Here are eight of the most popular language extensions:

<div class="marketplace-extensions-languages-curated"></div>

Go to the [Marketplace](https://marketplace.visualstudio.com/vscode) or use the integrated [Extensions view](/docs/configure/extensions/extension-marketplace.md) and search for your desired programming language to find snippets, code completion/IntelliSense providers, linters, debuggers, and more.

>**Note**: If you want to change the display language of VS Code (for example, to Chinese), see the [Display Language](/docs/configure/locales.md) topic.

## Language specific documentation

Learn about programming languages supported by VS Code. These include: [C++](/docs/languages/cpp.md) - [C&#35;](/docs/languages/csharp.md) - [CSS](/docs/languages/css.md) - [Dart](https://dart.dev/tools/vs-code) - [Dockerfile](/docs/azure/docker.md) - [F&#35;](/docs/languages/dotnet.md#create-an-f-hello-world-app) - [Go](/docs/languages/go.md) - [HTML](/docs/languages/html.md) - [Java](/docs/languages/java.md) - [JavaScript](/docs/languages/javascript.md) - [JSON](/docs/languages/json.md) - [Julia](/docs/languages/julia.md) - [Less](/docs/languages/css.md) -
[Markdown](/docs/languages/markdown.md) - [PHP](/docs/languages/php.md) - [PowerShell](/docs/languages/powershell.md) - [Python](/docs/languages/python.md) - [R](/docs/languages/r.md) - [Ruby](/docs/languages/ruby.md) - [Rust](/docs/languages/rust.md) - [SCSS](/docs/languages/css.md) - [Swift](/docs/languages/swift.md) - [T-SQL](/docs/languages/tsql.md) - [TypeScript](/docs/languages/typescript.md).

Click on any linked item to get an overview of how to use VS Code in the context of that language. Most language extensions also contain a summary of their core features in their README.

## Language features in VS Code

The richness of support varies across the different languages and their extensions:

* Syntax highlighting and bracket matching
* Smart completions (IntelliSense, Artificial Intelligence with [GitHub Copilot](/docs/editor/github-copilot.md))
* Linting and corrections
* Code navigation (Go to Definition, Find All References)
* Debugging
* Refactoring

## Enhance completions with AI

In VS Code, you can enhance your coding with artificial intelligence (AI), such as suggestions for lines of code or entire functions, fast documentation creation, and help creating code-related artifacts like tests.

[GitHub Copilot](https://copilot.github.com/) is an AI-powered code completion tool that helps you write code faster and smarter. You can use the [GitHub Copilot extension](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot) in VS Code to generate code, or to learn from the code it generates.

[![GitHub Copilot extension in the VS Code Marketplace](images/overview/copilot-extension.png)](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot)

You can learn more about how to get started with Copilot in the [Copilot documentation](/docs/editor/github-copilot.md).

## Change the language for the selected file

In VS Code, we default the language support for a file based on its filename extension. However, at times you may want to change language modes, to do this click on the language indicator - which is located on the right hand of the Status Bar. This will bring up the **Select Language Mode** dropdown where you can select another language for the current file.

![Language Selector](images/overview/languageselect.png)

**Tip**: You can get the same dropdown by running the **Change Language Mode** command (`kb(workbench.action.editor.changeLanguageMode)`).

## Language identifier

VS Code associates a language mode with a specific language identifier so that various VS Code features can be enabled based on the current language mode.

A language identifier is often (but not always) the lowercased programming language name. Note that casing matters for exact identifier matching ('Markdown' != 'markdown'). Unknown language files have the language identifier `plaintext`.

You can see the list of currently installed languages and their identifiers in the **Change Language Mode** (`kb(workbench.action.editor.changeLanguageMode)`) dropdown.

![language identifiers](images/overview/language-identifiers.png)

You can find a list of known identifiers in the [language identifier reference](/docs/languages/identifiers.md).

## Add a file extension to a language

You can add new file extensions to an existing language with the `setting(files.associations)` [setting](/docs/configure/settings.md).

For example, the setting below adds the `.myphp` file extension to the `php` language identifier:

```json
    "files.associations": {
        "*.myphp": "php"
    }
```

IntelliSense (`kb(editor.action.triggerSuggest)`) will show you the available language identifiers.

![Language ID IntelliSense](images/overview/language-id-intellisense.png)

## Next steps

Now you know that VS Code has support for the languages you care about. Read on...

* [Code Navigation](/docs/editing/editingevolved.md) - Peek and Go to Definition and more
* [Debugging](/docs/debugtest/debugging.md) - This is where VS Code really shines

## Common questions

### Can I contribute my own language service?

Yes you can! Check out the [example language server](/api/language-extensions/language-server-extension-guide.md) in the [VS Code Extension API](/api) documentation.

### What if I don't want to create a full language service, can I reuse existing TextMate bundles?

Yes, you can also add support for your favorite language through TextMate colorizers. See the [Syntax Highlight Guide](/api/language-extensions/syntax-highlight-guide.md) in the Extension API section to learn how to integrate TextMate `.tmLanguage` syntax files into VS Code.

### Can I map additional file extensions to a language?

Yes, with the `setting(files.associations)` [setting](/docs/configure/settings.md) you can map file extensions to an existing language either globally or per workspace.

Here is an example that will associate more file extensions to the PHP language:

```json
"files.associations": {
    "*.php4": "php",
    "*.php5": "php"
}
```

You can also configure full file paths to languages if needed. The following example associates all files in a folder `somefolder` to PHP:

```json
"files.associations": {
    "**/somefolder/*.*": "php"
}
```

Note that the pattern is a [glob pattern](/docs/editor/glob-patterns.md) that will match on the full path of the file if it contains a `/` and will match on the file name otherwise.

### How do I set the default language for new files?

Using the `setting(files.defaultLanguage)` [setting](/docs/configure/settings.md), you can map all new files to a default language. Whenever a new blank file is opened, the editor will be configured for that language mode.

This example will associate new files with the HTML language:

```json
  // The default language mode that is assigned to new files.
  "files.defaultLanguage": "html"
```
