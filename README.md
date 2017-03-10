# Apprentice Onboarding Packet

This is the onboarding packet for new apprentices. It should be given to them on
their first day.

## So You Just Started Mentoring a New Apprentice

Great! Here's how you use this:

* Print out `pdf/onboarding-packet.pdf` and fill in your name, then give it to your apprentice
* Make sure they know that we'd love feedback on this packet
* Encourage your apprentice to flip through the packet, but it's a reference, not a novel. Think of how you'd read a dictionary.
* You should read `pdf/mentor-handbook.pdf`.

## Editing

You should edit `markdown/onboarding-packet.md`, which is built into a lovely PDF in the `pdf/` directory.

Don't put links in `onboarding-packet.md`, put bare URLs instead so that they
show up when printed:

Bad:

    Try [Google](http://google.com).

Good:

    Try Google (http://google.com).

## Building

Requirements:

* [Pandoc](http://johnmacfarlane.net/pandoc/installing.html)
  - Can be installed via homebrew with `brew install pandoc`
* LaTeX
  - Use [BasicTeX](http://www.tug.org/mactex/morepackages.html), which is a much
    smaller download than full LaTeX.

Then:

    rake

View output:

    open pdf/onboarding-packet.pdf
    open pdf/get-a-job.pdf

## Releasing

To build a new PDF and release it to GitHub:

    rake release

# Credits

Thank you, [contributors](https://github.com/thoughtbot/apprenticeship/graphs/contributors)!

![thoughtbot](http://presskit.thoughtbot.com/images/thoughtbot-logo-for-readmes.svg)

This repository is maintained by [thoughtbot, inc](http://thoughtbot.com).

# License

This information is © 2014 thoughtbot, inc. It is distributed under the [Creative Commons
Attribution License](http://creativecommons.org/licenses/by/3.0/).

The names and logos for thoughtbot are trademarks of thoughtbot, inc.
