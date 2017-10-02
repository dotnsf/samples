# samples

## Cloudant Bulk Insert API

POST /dbname/_bulk_docs

{
 "docs": [
  { "title": "AAAA", "body", "aaaaaa" },
  { "title": "BBBB", "body", "bbbbbb" },
  { "title": "CCCC", "body", "cccccc" }
 ]
}

$ curl -u 'username:password' -XPOST 'https://username.cloudant.com/mydb/_bulk_docs' -H 'Content-Type: application/json' -d @prefs.json

