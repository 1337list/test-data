# Tweet object schema

Tweets are the basic atomic building block of all things Twitter. Tweets are also known as “status updates.” The Tweet object has a long list of ‘root-level’ attributes, including fundamental attributes such as id, created_at, and text. Tweet objects are also the ‘parent’ object to several child objects. Tweet child objects include user, entities, and extended_entities. Tweets that are geo-tagged will have a place child object.

<pre>
{
  "type": "Tweet",
  "internal_link": "<a href='https://github.com/1337list/test-data/tree/master/tweet_json'>Tweet schema</a>",
  "external_link": "<a href='https://developer.twitter.com/en/docs/tweets/data-dictionary/overview/tweet-object'>Twitter documentation</a>",
  "properties": {
    "created_at": {
      "type": "string",
      "description": "UTC time when this Tweet was created."
    },
    "id": {
      "type": "integer",
      "description": "The integer representation of the unique identifier for this Tweet. This number is <br>        greater than 53 bits and some programming languages may have difficulty/silent defects in interpreting <br>        it. Using a signed 64 bit integer for storing this identifier is safe. Use id_str for fetching the <br>        identifier to stay on the safe side. See Twitter IDs, JSON and Snowflake"
    },
    "id_str": {
      "type": "string",
      "description": "The string representation of the unique identifier for this Tweet. Implementations <br>        should use this rather than the large integer in id."
    },
    "text": {
      "type": "string",
      "description": "The actual UTF-8 text of the status update. See twitter-text for details on what <br>        characters are currently considered valid."
    },
    "source": {
      "type": "string",
      "description": "Utility used to post the Tweet, as an HTML-formatted string. Tweets from the Twitter <br>        website have a source value of web."
    },
    "truncated": {
      "type": "boolean",
      "description": "Indicates whether the value of the text parameter was truncated, for example, as a <br>        result of a retweet exceeding the original Tweet text length limit of 140 characters. Truncated text<br>         will end in ellipsis, like this ... Since Twitter now rejects long Tweets vs truncating them, the large <br>        majority of Tweets will have this set to false . Note that while native retweets may have their <br>        toplevel text property shortened, the original text will be available under the retweeted_status object and the truncated parameter will be set to the value of the original status (in most cases, false ). "
    },
    "in_reply_to_status_id": {
      "type": "int64",
      "description": "Nullable. If the represented Tweet is a reply, this field will contain the integer <br>        representation of the original Tweet’s ID."
    },
    "in_reply_to_status_id_str": {
      "type": "string",
      "description": "Nullable. If the represented Tweet is a reply, this field will contain the string <br>        representation of the original Tweet’s ID.."
    },
    "in_reply_to_user_id": {
      "type": "int64",
      "description": "Nullable. If the represented Tweet is a reply, this field will contain the integer <br>        representation of the original Tweet’s author ID. This will not necessarily always be the user <br>        directly mentioned in the Tweet."
    },
    "in_reply_to_user_id_str": {
      "type": "string",
      "description": "Nullable. If the represented Tweet is a reply, this field will contain the string <br>        representation of the original Tweet’s author ID. This will not necessarily always be the user <br>        directly mentioned in the Tweet. "
    },
    "in_reply_to_screen_name": {
      "type": "string",
      "description": "Nullable. If the represented Tweet is a reply, this field will contain the screen <br>        name of the original Tweet’s author."
    },
    "user": {
      "type": "User",
      "description": "The user who posted this Tweet. See User data dictionary for complete list of attributes.",
      "internal_link": "<a href='https://github.com/1337list/test-data/tree/master/tweet_json/user_object'>User object schema</a>",
      "external_link": "<a href= 'https://developer.twitter.com/en/docs/tweets/data-dictionary/overview/user-object'>Twitter documentation</a>"
    },
    "geo": {
      "type": "Object",
      "description": "Deprecated. Nullable. Use the coordinates field instead. This deprecated attribute <br>        has its coordinates formatted as [lat, long], while all other Tweet geo is formatted as [long, lat]."
    },
    "coordinates": {
      "type": "coordinates",
      "description": "Nullable. (formerly geo) Represents the geographic location of this Tweet as <br>        reported by the user or client application. The inner coordinates array is formatted as geoJSON <br>        (longitude first, then latitude)."
    },
    "place": {
      "type": "places",
      "description": "Nullable. When present, indicates that the tweet is associated (but not necessarily <br>        originating from) a Place ."
    },
    "contributors": {
      "type": "null",
      "description": "An explanation about the purpose of this instance."
    },
    "retweeted_status": {
      "type": "Tweet",
      "description": "Users can amplify the broadcast of Tweets authored by other users by retweeting .<br>         Retweets can be distinguished from typical Tweets by the existence of a retweeted_status <br>        attribute. This attribute contains a representation of the original Tweet <br>        that was retweeted. Note that retweets of retweets do not show representations <br>        of the intermediary retweet, but only the original Tweet. (Users can also unretweet <br>        a retweet they created by deleting their retweet.)",
      "internal_link": "<a href='https://github.com/1337list/test-data/tree/master/tweet_json'>Tweet schema</a>",
      "external_link": "<a href= 'https://developer.twitter.com/en/docs/tweets/data-dictionary/overview/tweet-object'>Twitter documentation</a>"
    },
    "is_quote_status": {
      "type": "boolean",
      "description": "Indicates whether this is a Quoted Tweet."
    },
    "quote_count": {
      "type": "integer",
      "description": "Nullable. Indicates approximately how many times this Tweet has been quoted by <br>        Twitter users."
    },
    "reply_count": {
      "type": "integer",
      "description": "Number of times this Tweet has been replied to."
    },
    "retweet_count": {
      "type": "integer",
      "description": "Number of times this Tweet has been retweeted."
    },
    "favorite_count": {
      "type": "integer",
      "description": "Nullable. Indicates approximately how many times this Tweet has been liked by<br>         Twitter users."
    },
    "entities": {
      "type": "Entities",
      "description": "Entities which have been parsed out of the text of the Tweet. Additionally see <br>        Entities in Twitter Objects .",
      "internal_link": "<a href= 'https://github.com/1337list/test-data/tree/master/tweet_json/entities_object'>Entities schema</a>",
      "external_link": "<a href= 'https://developer.twitter.com/en/docs/tweets/data-dictionary/overview/entities-object'>Twitter documentation</a>"
    },
    "favorited": {
      "type": "boolean",
      "description": "Nullable. Indicates whether this Tweet has been liked by the authenticating user."
    },
    "retweeted": {
      "type": "boolean",
      "description": "Indicates whether this Tweet has been Retweeted by the authenticating user."
    },
    "filter_level": {
      "type": "string",
      "description": "Indicates the maximum value of the filter_level parameter which may be used and <br>        still stream this Tweet. So a value of medium will be streamed on none, low, and medium streams."
    },
    "lang": {
      "type": "string",
      "description": "Nullable. When present, indicates a BCP 47 language identifier corresponding to <br>        the machine-detected language of the Tweet text, or und if no language could be detected.<br>         See more documentation HERE"
    },
    "timestamp_ms": {
      "type": "string",
      "description": "An explanation about the purpose of this instance."
    }
  }
}
</pre>
