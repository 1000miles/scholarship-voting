# Scholarship Submissions Review

## How to set up the voting tool

1. Fork this repo and rename it properly, if needed.
2. Adopt or change the voting scales under the class `stat` in the file `index.html` (at the moment we use 0-3).
3. Make sure a Google Spreadsheet with reponses is existent and delete or hide all columns that are not needed for the voting.
4. Ensure the name of the Google Spreadsheet columns match with the names of the proposal values.

**Examples:**

Google Spreadsheet column names:
    - "Motivation"
    - "About"
    - empty

```js

function showInfo(data) {
    totalRows = data.length;
    data = data.map(function (proposal) {
    proposal.topicofpresentation = proposal["motivation"];
    proposal.summary = proposal["about"];
    proposal.extra = "";
    proposal.sheetRowNumber = proposal.rowNumber + 1;
    return proposal;
    })
    ...
}
```

5. In the `export-container` class of the file `index.html` change the email address to yours.
6. Make sure the tab name in your Google Spreadsheet is `Form Reponses 1`.
7. Publish the corresponding Google Spreadsheet under `File` > `Publish to the web`.
8. Once done with the voting, remember to unpublish the Google Spreadsheet again.

## How to use the voting tool

### Web

1. Go to the published URL of your repo, e.g. https://1000miles.github.io/scholarship-voting (gh-pages)
2. When prompted, paste the URL of the published Google Spreadsheet.
3. Start voting!
4. When done with the voting, copy the result (from top to down) of the textarea at the bottom.


```
# Timestamp, Voting Value

09/2/2019 12:01:18,1,
10/15/2018 12:22:05,2,
11/03/2018 12:53:17,3,
```

Troubleshooting:
- Since your voting result is not saved into any database, do not close the browser window or delete the cache during the voting process.
- If the voting in the browser does not work anymore, make sure there is no other window tab open with the same URL.

### Locally

Run under a webserver, the easiest on a Mac is:

```sh
python -m SimpleHTTPServer
open http://127.0.0.1:8000/
````

To end the httpd server, close the terminal or run

```sh
fg
```
and then hit ctrl-c
