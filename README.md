# Apprentice Onboarding Packet

This is the onboarding packet for new apprentices. It should be given to them on
their first day.


## Editing

You should edit `onboarding-packet.md`, which is built into a lovely PDF in the `pdf/` directory.

## Building

Requirements:
* [Pandoc](http://johnmacfarlane.net/pandoc/installing.html)
* LaTeX
  - Use [BasicTeX](http://www.tug.org/mactex/morepackages.html), which is a much
    smaller download than full LaTeX.

Then:

    rake && open book/*.pdf

## Releasing

To build a new PDF and release it to GitHub:

    rake release
