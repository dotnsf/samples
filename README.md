# samples

## Cloudant Bulk Insert API

POST /(dbname)/_bulk_docs

{
 "docs": [
  { "code": 1, "prefecture": "北海道", "capital": "札幌市", "lat": 43.06417, "lng": 141.34694 },
  { "code": 2, "prefecture": "青森県", "capital": "青森市", "lat": 40.82444, "lng": 140.74 },
     :
  { "code": 47, "prefecture": "沖縄県", "capital": "那覇市", "lat": 26.2125, "lng": 127.68111 }
 ]
}

- $ curl -u 'username:password' -XPOST 'https://username.cloudant.com/mydb/_bulk_docs' -H 'Content-Type: application/json' -d @prefs.json

## Cloudant Design Document API

PUT /(dbname)/_design/(viewname)

{
 "language": "javascript",
 "views": {
  "xxxxview": {
   "map": "function(doc){ ... }"
  }
 },
 "lists": {
  "xxxxlist": "function( head, row ){ ... }" 
 },
 "shows": {
  "xxxxshow": "(function( doc, req ){ if( doc ){ ... }else{ ... }})"
 }
}


### View Design Document

- $ curl -u 'username:password' -XPOST 'https://username.cloudant.com/mydb/_design/nosea' -H 'Content-Type: application/json' -d @nosea_view.json

    - https://username.cloudant.com/mydb/_design/nosea

        - https://username.cloudant.com/mydb/_design/nosea/_view/nosea

### List Design Document

- $ curl -u 'username:password' -XPOST 'https://username.cloudant.com/mydb/_design/nosea' -H 'Content-Type: application/json' -d @nosea_list.json

    - https://username.cloudant.com/mydb/_design/nosea

        - https://username.cloudant.com/mydb/_design/nosea/_list/nosea/nosea

            - リンク先へはいけない

### Show Design Document

- $ curl -u 'username:password' -XPOST 'https://username.cloudant.com/mydb/_design/nosea' -H 'Content-Type: application/json' -d @nosea_show.json

    - https://username.cloudant.com/mydb/_design/nosea

        - https://username.cloudant.com/mydb/_design/nosea/_list/nosea/nosea

            - リンク先へジャンプ可

        - https://username.cloudant.com/mydb/_design/nosea/_show/nosea/(doc.id)


