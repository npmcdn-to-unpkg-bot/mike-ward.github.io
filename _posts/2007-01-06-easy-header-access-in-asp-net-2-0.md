---
layout: post  
title: 'Easy Header Access in ASP.NET 2.0'
---
Recently, I needed to add a header attribute programmatically to an ASP.NET page. [Ryan Farley](http://ryanfarley.com/blog/archive/2006/03/24/18930.aspx) posts an excellent article detailing some new **ASP.NET 2.0** API's that make it easy. 

To change a page's title: 

    this.Header.Title = "This is the new page title.";

To add a style attribute for the page: 

    Style style = new Style();
    style.ForeColor = System.Drawing.Color.Navy;
    style.BackColor = System.Drawing.Color.LightGray;
     
    // Add the style to the header for the body of the page
    this.Header.StyleSheet.CreateStyleRule(style, null, "body");

To add a style-sheet to : 

    HtmlLink link = new HtmlLink();
    link.Attributes.Add("type", "text/css");
    link.Attributes.Add("rel", "stylesheet");
    link.Attributes.Add("href", "~/newstyle.css");
    this.Header.Controls.Add(link);
