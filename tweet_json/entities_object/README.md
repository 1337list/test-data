# Entities object schema
Entities provide metadata and additional contextual information about content posted on Twitter. The entities section provides arrays of common things included in Tweets: hashtags, user mentions, links, stock tickers (symbols), Twitter polls, and attached media. These arrays are convenient for developers when ingesting Tweets, since Twitter has essentially pre-processed, or pre-parsed, the text body. Instead of needing to explicitly search and find these entities in the Tweet body, your parser can go straight to this JSON section and there they are.

Beyond providing parsing conveniences, the entities section also provides useful ‘value-add’ metadata. For example, if you are using the Enhanced URLs enrichment, URL metadata include fully-expanded URLs, as well as associated website titles and descriptions. Another example is when there are user mentions, the entities metadata include the numeric user ID, which are useful when making requests to many Twitter APIs.

Every Tweet JSON payload includes an entities section, with the minimum set of hashtags, urls, user_mentions, and symbols attributes, even if none of those entities are part of the Tweet message.
<pre>
{
  "type": "Entities",
  "description": "Entities which have been parsed out of the text of the Tweet. Additionally <br>        see Entities in Twitter Objects .",
  "internal_link": "<a href= 'https://github.com/1337list/test-data/tree/master/tweet_json' >Entities schema</a>",
  "external_link": "<a href= 'https://developer.twitter.com/en/docs/tweets/data-dictionary/overview/entities-object'>Twitter documentation</a>",
  "properties": {
    "hashtags": {
      "type": "Array of Hashtag Objects",
      "description": "Represents hashtags which have been parsed out of the Tweet text.",
      "internal_link": "<a href= 'https://github.com/1337list/test-data/tree/master/tweet_json/hashtag' >Hashtag schema</a>",
      "external_link": "<a href= 'https://developer.twitter.com/en/docs/tweets/data-dictionary/overview/entities-object#hashtag'>Twitter documentation</a>"
    },
    "urls": {
      "type": "Array of URL Objects",
      "description": "Represents URLs included in the text of a Tweet.",
      "internal_link": "<a href= 'https://github.com/1337list/test-data/tree/master/tweet_json/url' >Url schema</a>",
      "external_link": "<a href= 'https://developer.twitter.com/en/docs/tweets/data-dictionary/overview/entities-object#urls'>Twitter documentation</a>"
    },
    "user_mentions": {
      "type": "Array of User Mention Objects",
      "description": "Represents other Twitter users mentioned in the text of the Tweet.",
      "internal_link": "<a href= 'https://github.com/1337list/test-data/tree/master/tweet_json/user_mention' >User mention schema</a>",
      "external_link": "<a href= 'https://developer.twitter.com/en/docs/tweets/data-dictionary/overview/entities-object#mentions'>Twitter documentation</a>"
    },
    "symbols": {
      "type": "Array of Symbol Objects",
      "description": "Represents symbols, i.e. $cashtags, included in the text of the Tweet.",
      "internal_link": "<a href= 'https://github.com/1337list/test-data/tree/master/tweet_json/symbol' >Symbol schema</a>",
      "external_link": "<a href= 'https://developer.twitter.com/en/docs/tweets/data-dictionary/overview/entities-object#symbols'>Twitter documentation</a>"
    }
  }
}
</pre>
