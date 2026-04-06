---
layout: post
title:  "Hello World: Building this website without understanding the internet"
date:   2026-04-05 15:55:04 -0400
categories: website
---
Hello! If you're reading this many years in the future, hopefully there are many more blog posts after this one. Otherwise, it seems that this little blog experiment has sadly failed. Regardless, I finally gathered the motivation to just sit down for a couple hours and get some kind of structure set up.

So, I went over to MITERS at noon and told myself I wouldn't leave until I had at least a skeleton of a website up and running. It was at this point that I realized I have no idea how to create a website or even how they really work. I looked at a [couple][ben-katz-web] [past][austinb-web] [MITERS][franklin-web] [blogs][birkel-web], and they seemed to be quite varied, although I did recognize some common features. Visuals are great and all, but this still didn't give me a clue on how to actually make a website. So I went to the best free source of information I know, the [MITERS][miters-web] Discord server. [Oliver][oliver-web] recommended using [Github Pages][github-pages-web] as it provide free hosting as well as various other [Three Letter Acronyms][tla-web] (TLAs) that I honestly only vaguely understand the utility of (DNS, SSL, TLS, etc etc...). [Jonhenry][jonhenry-web] also confirmed that Github Pages was a good choice to minimize the amount of code I would have to write, so that was good enough for me<sup>1</sup> <sup>2</sup> <sup>3</sup>.

So with the architecture decided, it was time to find a domain and get started. Or at least that's what I should have done. The reality is that I had gotten overexcited and already bought the domain [intentionally-aimless.com][nevin-web]<sup>4</sup> and only asked about hosting when I realized I had no idea what to do next.

![Cloudflare domain successfully registered email][cloudflare-domain]
<center><em>Domain purchased from Cloudflare!</em></center><br>

The story behind the name *intentionally aimless* is somewhat silly. I actually came up with this name at some point in high school while pondering making a [YouTube channel][nevin-yt]. I often find myself drifting from project to project as my interests in different fields ebb and flow, so the name still seems appropriate.

To actually set up my site on Github Pages, I vaguely followed these tutorials:
- [Github Pages Quickstart](https://docs.github.com/en/pages/quickstart)
- [Using a Custom Domain for Github Pages](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/about-custom-domains-and-github-pages)
- [Using https with Github Pages](https://docs.github.com/en/pages/getting-started-with-github-pages/securing-your-github-pages-site-with-https)
- [Verifying a Custom Domain for Github Pages](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/verifying-your-custom-domain-for-github-pages)
- [Managing a Custom Domain for Github Pages](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site)

There were various issues in actually getting this implemented including adding DNS records to the Cloudflare page properly and ensuring that it was not using the Cloudflare proxy so Github Pages could do all of the authentication/verification stuff it needed to do.

However, I was eventually able to get up in all its unstyled glory.

![Initial webpage, only text reads "Nevin-Thinagar.github.io][initial-commit]
<center><em>Website up an running, albeit in a very rudimentary form</em></center><br>

Actually, the webpage started out with marginally more styling than this (I, unfortunately, do not have an image of this). However, I then attempted to implement [Jekyll][jekyll-web] in a rather silly way<sup>5</sup> and ended up somehow getting rid of this styling. So, I decided to figure out how Jekyll actually worked and install it properly. It turns out I first had to install [Ruby][ruby-web] then run the following commands:

{% highlight ruby %}
  gem install bundler jekyll
  jekyll new . --force
  bundle install
{% endhighlight %}

This added all the requisite files to my repository and set up the base layouts and styling. At first I thought this change hadn't worked since the website still looked the same. But it turns out this was just my browser caching the website locally instead of loading it from the server. A quick `CTRL + SHIFT + R` seemed to easily resolve this issue.

![Website in the Minima V2.5.2 theme][jekyll-welcome]
<center><em>Website ft. the Minima V2.5.2 theme</em></center><br>

I also realized I am not very competent when it comes to writing in Markdown.

![Website with dubious markdown formatting][markdown-struggles]
<center><em>Why are the footnotes ugly and using arrow emojis</em></center><br>

I have now gotten to the point where this post becomes self-referential. The formatting is in a place that I am relatively happy with, although there are some things with styling that I want to fix. This is made slightly more complex by the fact that the theme I am currently using, [Minima][minima-web], is preparing for a relatively major update. As such, I don't want to customize too much right now just for it to become outdated in a few months.

I should also mention that I decided to host my images on [Cloudinary][cloudinary-web] since it automatically compresses them for faster loading and is also free up to 25 GB. I don't know how fast that will fill up but hopefully it lasts for a good while.

In addition to more styling, there are still many features that I want to add to this site and my development/writing process:
- Comments
- Search
- Local page preview (Vscode's built-in markdown preview doesn't seem to want to process everything like on the website)
- Category filters
- More things I haven't thought of yet

Most of all, I think I need to get better at this whole blog writing thing. I feel like this post has too many words and not enough images. Also it's kind of fun to read, but I think I can do better.

Anyways, I think I'll save that for the next post as it is now 4 AM (not continuous work since noon, fortunately) and I am tired.

Goodnight.

<!--Footnotes-->
<sup style="color:#666">1</sup> <small style="color:#666">[Anhad][anhad-web] said he uses Squarespace which costs ~$100 a year and [Vaughn][vaughn-web] recommended [Vercel][vercel-web]. I ended up deciding against these, though, as Github Pages was free (Vercel also is) and I already had a Github account.</small>\
<sup style="color:#666">2</sup> <small style="color:#666">I also briefly pondered self-hosting like [Andrew][andrew-web] does, before realizing I want to get this up and running without it taking several months. Also, I don't have a homelab setup.</small>\
<sup style="color:#666">3</sup> <small style="color:#666">I also considered using MIT's hosting service for student and other websites. However, this (to the best of my knowledge) expires after I graduate so I wanted to set up something a little more permanent.</small>\
<sup style="color:#666">4</sup> <small style="color:#666">Only $10.46/year!</small>\
<sup style="color:#666">5</sup> <small style="color:#666">I simply added a _config.yml file to the repo without doing any of the other parts.</small>

<!--Image links-->
[cloudflare-domain]: https://res.cloudinary.com/dwyrlx60x/image/upload/q_auto/f_auto/v1775425354/domain-registered_lhhrdd.png "I didn't think it would be this easy"
[initial-commit]: https://res.cloudinary.com/dwyrlx60x/image/upload/q_auto/f_auto/v1775459747/initial-commit_zz7cb6.png "Hello World!"
[jekyll-welcome]: https://res.cloudinary.com/dwyrlx60x/image/upload/q_auto/f_auto/v1775461119/jekyll-welcome_ntgmgl.png "Why is it even called Jekyll?"
[markdown-struggles]: https://res.cloudinary.com/dwyrlx60x/image/upload/q_auto/f_auto/v1775462312/markdown-struggles_nre3uw.png "I am yet to use a single heading"

<!--Website links-->
[ben-katz-web]: https://robot-daycare.com/
[austinb-web]: https://brushless.zone/
[franklin-web]: https://www.franklinwei.com/blog/
[jonhenry-web]: https://www.jonhenryposs.com/
[birkel-web]: https://andrewbirkel.com/
[miters-web]: https://miters.mit.edu/
[oliver-web]: https://olivertrevor.tech/
[github-pages-web]: https://docs.github.com/en/pages
[tla-web]: https://en.wikipedia.org/wiki/Three-letter_acronym
[anhad-web]: https://www.anhadsawhney.com/
[vaughn-web]: https://www.vkhouri.dev/
[vercel-web]: https://vercel.com/
[nevin-web]: https://intentionally-aimless.com/
[andrew-web]: https://www.kyoungwanwoo.com/
[nevin-yt]: https://www.youtube.com/@NevinThinagar
[jekyll-web]: https://jekyllrb.com/
[ruby-web]: https://rubyinstaller.org/downloads/
[minima-web]: https://github.com/jekyll/minima
[cloudinary-web]: https://cloudinary.com/
