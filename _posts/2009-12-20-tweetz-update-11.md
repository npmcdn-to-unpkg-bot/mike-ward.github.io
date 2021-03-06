---
layout: post
title: 'tweetz Update #11'
---
Just in time for Christmas, it’s an update to tweetz! (Well, OK, Christmas has nothing to do with it but it made for a cheap and flashy introduction). So what’s new?

  * Update dialog moved to a flyout 
  * Enter key sends updates option added 

And here are the screen-shots

![update](/cdn/images/blog/tweetzUpdate11_C1DA/update.jpg)

![sendonenter](/cdn/images/blog/tweetzUpdate11_C1DA/sendonenter.jpg)

The "Flyout" dialog (that’s what they’re called in gadget lingo) was necessary to get around a performance issue the gadget was experiencing. Over time, as more twitter updates arrive, the “Send Update” text box got unacceptably slow. There’s no reason code-wise why it should slow down but it happens none the less. Chalk it up to another one of those strange Windows gadget behaviors (and there are a lot of them, believe me).

I found through experimentation that the "Flyout" dialog didn’t experience this same detrimental behavior. It’s not my first choice but this is just one of those “concessions” you sometimes have to make in a program.

In use, the "Flyout" behaves in a similar fashion to the previous embedded dialog. The one exception is that if the gadget loses focus, the "Flyout" dialog closes. The contents of the update are still there so there’s no damage but it does mean an extra mouse click or two on occasion when doing a copy and paste for instance.

The “Enter key sends updates” option restores the original behavior of sending updates when the enter key is pressed. Some complained that they would send updates accidentally so I disabled it. After I disabled it, others complained that they missed the feature. Now you can choose.

Future Updates:

The only new feature I have planned at this time is to add a "more" link. It will appear as the last item in the tweet list. This is similar to how it works on the twitter home page.

Available on the [downloads page](/downloads).
