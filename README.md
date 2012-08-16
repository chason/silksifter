NAME
==========

silksifter

DESCRIPTION
==========

Website Data Gatherer

Silksifter is an API and tool for processing information on a website. Send it
a JSON object where the values are the CSS selector you want to extract.
Once the data is saved, you can use plugin filters to process the data.

SYNOPSIS
==========

To process a website you will want to send a `POST` request to
`/process/web/<name>` replacing `<name>` with the name of your data. You
should `POST` a JSON object that looks something like this:

    {
        'url': 'http://example.com/attendees',
        'title': 'ExampleCon Attendees',
        'keep': '7',
        'filters': \['klout','pagerank'\],
        'schema':
        {
            'name': '.fullname',
            'twitter': '.twitter',
            'website': '.info a\[href\]',
        }
    },

This will return a JSON object without the filtered data yet:

    \[{
        'name': 'Alan Turing',
        'twitter': '',
        'website': 'http://www.turing.org.uk',
    },
    {
        'name': 'Mark Mullenweg',
        'twitter': '@photomatt',
        'website': 'http://ma.tt',
    },]


