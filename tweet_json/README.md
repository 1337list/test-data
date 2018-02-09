# Tweet JSON
Tweet JSON test data and helpful resources.
<pre>
{
  "$id": "http://example.com/example.json",
  "type": "object",
  "definitions": {},
  "$schema": "http://json-schema.org/draft-06/schema#",
  "properties": {
    "created_at": {
      "$id": "/properties/created_at",
      "type": "string"
    },
    "id": {
      "$id": "/properties/id",
      "type": "integer"
    },
    "id_str": {
      "$id": "/properties/id_str",
      "type": "string"
    },
    "text": {
      "$id": "/properties/text",
      "type": "string"
    },
    "source": {
      "$id": "/properties/source",
      "type": "string"
    },
    "truncated": {
      "$id": "/properties/truncated",
      "type": "boolean"
    },
    "in_reply_to_status_id": {
      "$id": "/properties/in_reply_to_status_id",
      "type": "null"
    },
    "in_reply_to_status_id_str": {
      "$id": "/properties/in_reply_to_status_id_str",
      "type": "null"
    },
    "in_reply_to_user_id": {
      "$id": "/properties/in_reply_to_user_id",
      "type": "null"
    },
    "in_reply_to_user_id_str": {
      "$id": "/properties/in_reply_to_user_id_str",
      "type": "null"
    },
    "in_reply_to_screen_name": {
      "$id": "/properties/in_reply_to_screen_name",
      "type": "null"
    },
    "user": {
      "ref": "<a href="https://github.com/1337list/test-data/blob/master/tweet_json/tweet_json_schema.json#L5" title="assign documentation">user_schema</a>"
    },
    "geo": {
      "$id": "/properties/geo",
      "type": "null"
    },
    "coordinates": {
      "$id": "/properties/coordinates",
      "type": "null"
    },
    "place": {
      "$id": "/properties/place",
      "type": "null"
    },
    "contributors": {
      "$id": "/properties/contributors",
      "type": "null"
    },
    "retweeted_status": {
      "ref": "<a href="https://github.com/1337list/test-data/blob/master/tweet_json/tweet_json_schema.json#L5" title="assign documentation">user_schema</a>"
    },
    "is_quote_status": {
      "$id": "/properties/is_quote_status",
      "type": "boolean"
    },
    "quote_count": {
      "$id": "/properties/quote_count",
      "type": "integer"
    },
    "reply_count": {
      "$id": "/properties/reply_count",
      "type": "integer"
    },
    "retweet_count": {
      "$id": "/properties/retweet_count",
      "type": "integer"
    },
    "favorite_count": {
      "$id": "/properties/favorite_count",
      "type": "integer"
    },
    "entities": {
      "ref": "<a href="https://github.com/1337list/test-data/blob/master/tweet_json/tweet_json_schema.json#L5" title="assign documentation">user_schema</a>"
    },
    "favorited": {
      "$id": "/properties/favorited",
      "type": "boolean"
    },
    "retweeted": {
      "$id": "/properties/retweeted",
      "type": "boolean"
    },
    "filter_level": {
      "$id": "/properties/filter_level",
      "type": "string"
    },
    "lang": {
      "$id": "/properties/lang",
      "type": "string"
    },
    "timestamp_ms": {
      "$id": "/properties/timestamp_ms",
      "type": "string"
    }
  }
}
</pre>
