---
tags:
  - trip-tagger
---
GET tagger-test/_search
{

  "query": {
    "constant_score": {
      "filter": {
        "term": {
          "tag": "something"
        }
      }
    }
  }
}

POST tagger-test/all/4
{
  "tripUUID": "qwerty",
  "clientUUID": "uiop",
  "tag": "success"
}

DELETE tagger-test/all/7

GET tagger-test/_search
{
  "query": {
    "bool": {
      "must": [
        { "match_all": {} }
      ]
    }
  }
}

GET tagger-test/all/_search
{
  "query": {
    "constant_score": {
      "filter": {
        "terms": {
          "tag": ["success", "example"]
        }
      }
    }
  }
}

GET tagger-test/_search
{
  "aggs": {
    "all": {
      "terms": {
        "field": "tripUUID",
        "size": 1
      }
    }
  }
}

GET tagger-test/all/_search
{
   "size": 0,
   "query" : {
        "bool" : {
               "should" : [
                  { "term" : { "tag" : "success" } },
                  { "term" : { "tag" : "fail" } }
               ]
         }
    },
    "aggs":{
        "unique_ids": {
            "terms": {
                "field": "tripUUID"
            }
        }
    }
}

PUT tagger-test/_mapping/all
{
  "properties": {
    "tripUUID": {
      "type": "text",
      "fielddata": true
    },
    "clientUUID": {
      "type": "text",
      "fielddata": true
    },
    "tag": {
      "type": "text",
      "fielddata": true
    }
  }
}