---
layout: post  
title: 'Introducing Nancy.Markdown.Blog'
---

`TL;DR` - [GitHub - Nancy.Markdown.Blog](https://github.com/mike-ward/Nancy.Markdown.Blog)

I wanted to write my blog posts in [Markdown](http://daringfireball.net/projects/markdown/syntax). I write my GitHub docs and [Stack Overflow](http://stackoverflow.com) questions in Markdown, so why not my blog posts? I also wanted to lose my dependency on [Windows Live Writer](http://www.wikiwand.com/en/Windows_Live_Writer). Live Writer is a (very) nice program for authoring, but it hasn't been updated in a long time. I get this feeling it might go away soon.

My goal for Nancy.Markdown.Blog was to make it minimal. I figure since you're a programmer, you can add whatever fluff is needed for your application. From my perspective, a blog engine needs to to three things.

- Render content from storage
- Provide navigation
- Emit RSS

In a nutshell, that's Nancy.Markdown.Blog. There's a example web site in the repository that you're welcome to appropriate for your own use.

I store my posts in plain old files. There's no required file format (or the type of storage for that matter), however, there is a convenience method for reading posts from a `Stream`. It uses the first line as the **title** of the post and the second line is the **date** of the post. Any of the date formats recognized by .NET's `DateTime` struct are permitted. The rest of the lines are the **content** of the post.

Posts can be, "future dated". Posts with dates in the future are not displayed.

The dialect of Markdown supported is similar to [PHP Markdown Extra](https://michelf.ca/projects/php-markdown/extra/), meaning goodies like code-fences and tables are supported.

Nancy.Markdown.Blog generates [slugs](http://codex.wordpress.org/Glossary#Post_Slug), which you can use in your permalinks. The slug code is the same as used by Stack Overflow, so it's robust and language sensitive. Permalinks are also generated for posts. The default format is:

    baseurl+blog/post/YYYY/MM/DD/Slug

The default permalink generator can be overridden.

And since you love Markdown, I added a method to the `HtmlHelpers` class that allows insertion of, "Markdown Islands" into a Razor view. I use it to author the content of the other pages on this web site. I just find it easier than writing in markup (pun intended).

    <div>
    @Html.Markdown(@"
    ## About HTML.Markdown ##
    ---
    
    It's easy to include Markdown in other pages.
    
    Who needs HTML?
    ")
    </div>

Finally, you can add Nancy.Markdown.Blog to a project using Nuget.

    PM> install-package Nancy.Markdown.Blog 