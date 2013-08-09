# Apprentice Onboarding Packet

This is the onboarding packet for new apprentices. It should be given to them on
their first day.

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
