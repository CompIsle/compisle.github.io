# Bootstrap Template

There is a file called %AppData%\Roaming\Code\User\snippets\html.json - although I would NOT try to edit it directly, instead in Code select 'User Snippets' from the Settings and then select html from the drop down of types. If the content were as below then you would have something to insert a default Bootstrap template in an empty file. Note "The prefix is what is used to trigger the snippet".

```json
{
    // Place your snippets for html here. Each snippet is defined under a snippet name and has a prefix, body and
    // description. The prefix is what is used to trigger the snippet and the body will be expanded and inserted. Possible variables are:
    // $1, $2 for tab stops, $0 for the final cursor position, and ${1:label}, ${2:another} for placeholders. Placeholders with the
    // same ids are connected.
    // Example:
    // "Print to console": {
    //  "prefix": "log",
    //  "body": [
    //   "console.log('$1');",
    //   "$2"
    //  ],
    //  "description": "Log output to console"
    // }
   
    "New bootstrap file": {
      "prefix": "boott",
      "body": [
        "<!DOCTYPE html>",
        "<html>",
        "<head>",
        "<meta charset='UTF-8'>",
        "<meta name='viewport' content='width=device-width, initial-scale=1'>",
        "<title></title>",
        "<link href='https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css' rel='stylesheet'>",
        "<link rel='stylesheet' href='css/styles.css'>",
  
        "</head>",
        "<body>",
        "$0",
        "<script src='https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/js/bootstrap.bundle.min.js'></script>",
        "</body>",
        "</html>"
      ],
      "description": "boilerplate for new bootstrap file"
    }
}
```
