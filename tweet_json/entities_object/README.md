# Entities object schema
Entities provide metadata and additional contextual information about content posted on Twitter. The entities section provides arrays of common things included in Tweets: hashtags, user mentions, links, stock tickers (symbols), Twitter polls, and attached media. These arrays are convenient for developers when ingesting Tweets, since Twitter has essentially pre-processed, or pre-parsed, the text body. Instead of needing to explicitly search and find these entities in the Tweet body, your parser can go straight to this JSON section and there they are.

Beyond providing parsing conveniences, the entities section also provides useful ‘value-add’ metadata. For example, if you are using the Enhanced URLs enrichment, URL metadata include fully-expanded URLs, as well as associated website titles and descriptions. Another example is when there are user mentions, the entities metadata include the numeric user ID, which are useful when making requests to many Twitter APIs.

Every Tweet JSON payload includes an entities section, with the minimum set of hashtags, urls, user_mentions, and symbols attributes, even if none of those entities are part of the Tweet message.
<pre>
{
  "type": "User",
  "internal_link": "<a href= 'https://github.com/1337list/test-data/tree/master/tweet_json/user_object' >User object schema</a>",
  "external_link": "<a href= 'https://developer.twitter.com/en/docs/tweets/data-dictionary/overview/user-object' >Twitter documentation</a>",
  "properties": {
    "id": {
      "type": "int64",
      "description": "The integer representation of the unique identifier for this User. <br>        This number is greater than 53 bits and some programming languages may have difficulty/silent <br>        defects in interpreting it. Using a signed 64 bit integer for storing this identifier is safe. <br>        Use id_str for fetching the identifier to stay on the safe side."
    },
    "id_str": {
      "type": "string",
      "description": "The string representation of the unique identifier for this User. <br>        Implementations should use this rather than the large, possibly un-consumable integer in id."
    },
    "name": {
      "type": "string",
      "description": "The name of the user, as they’ve defined it. Not necessarily a person’s name. Typically <br>        capped at 20 characters, but subject to change."
    },
    "screen_name": {
      "type": "string",
      "description": "The screen name, handle, or alias that this user identifies themselves with. screen_names <br>        are unique but subject to change. Use id_str as a user identifier whenever possible. <br>        Typically a maximum of 15 characters long, but some historical accounts may exist with longer names."
    },
    "location": {
      "type": "string",
      "description": "Nullable . The user-defined location for this account’s profile. Not necessarily a location, <br>        nor machine-parseable. This field will occasionally be fuzzily interpreted by the Search service."
    },
    "url": {
      "type": "null",
      "description": "Nullable . A URL provided by the user in association with their profile."
    },
    "description": {
      "type": "string",
      "description": "Nullable . The user-defined UTF-8 string describing their account."
    },
    "translator_type": {
      "type": "string",
      "description": "An explanation about the purpose of this instance."
    },
    "protected": {
      "type": "boolean",
      "description": "When true, indicates that this user has chosen to protect their Tweets."
    },
    "verified": {
      "type": "boolean",
      "description": "When true, indicates that the user has a verified account. See Verified Accounts ."
    },
    "followers_count": {
      "type": "integer",
      "description": "The number of followers this account currently has. Under certain conditions of duress,<br>         this field will temporarily indicate “0”."
    },
    "friends_count": {
      "type": "integer",
      "description": "The number of users this account is following (AKA their “followings”). Under certain <br>        conditions of duress, this field will temporarily indicate “0”."
    },
    "listed_count": {
      "type": "integer",
      "description": "The number of public lists that this user is a member of."
    },
    "favourites_count": {
      "type": "integer",
      "description": "The number of Tweets this user has liked in the account’s lifetime. British spelling <br>        used in the field name for historical reasons."
    },
    "statuses_count": {
      "type": "integer",
      "description": "The number of Tweets (including retweets) issued by the user."
    },
    "created_at": {
      "type": "string",
      "description": "he UTC datetime that the user account was created on Twitter."
    },
    "utc_offset": {
      "type": "integer",
      "description": "Nullable . The offset from GMT/UTC in seconds."
    },
    "time_zone": {
      "type": "string",
      "description": "Nullable . A string describing the Time Zone this user declares themselves within."
    },
    "geo_enabled": {
      "type": "boolean",
      "description": "When true, indicates that the user has enabled the possibility of geotagging their Tweets. <br>        This field must be true for the current user to attach geographic data when using POST statuses / update ."
    },
    "lang": {
      "type": "string",
      "description": "The BCP 47 code for the user’s self-declared user interface language. May or may <br>        not have anything to do with the content of their Tweets."
    },
    "contributors_enabled": {
      "type": "boolean",
      "description": "Indicates that the user has an account with “contributor mode” enabled, allowing <br>        for Tweets issued by the user to be co-authored by another account. Rarely true (this is a legacy field)."
    },
    "is_translator": {
      "type": "boolean",
      "description": "Deprecated. When true, indicates that the user is a participant in Twitter’s <br>        translator community."
    },
    "profile_background_color": {
      "type": "string",
      "description": "The hexadecimal color chosen by the user for their background."
    },
    "profile_background_image_url": {
      "type": "string",
      "description": "A HTTP-based URL pointing to the background image the user has uploaded <br>        for their profile."
    },
    "profile_background_image_url_https": {
      "type": "string",
      "description": "A HTTPS-based URL pointing to the background image the user has uploaded <br>        for their profile."
    },
    "profile_background_tile": {
      "type": "boolean",
      "description": "When true, indicates that the user’s profile_background_image_url should <br>        be tiled when displayed."
    },
    "profile_link_color": {
      "type": "string",
      "description": "The hexadecimal color the user has chosen to display links with in their <br>        Twitter UI."
    },
    "profile_sidebar_border_color": {
      "type": "string",
      "description": "The hexadecimal color the user has chosen to display sidebar borders with <br>        in their Twitter UI."
    },
    "profile_sidebar_fill_color": {
      "type": "string",
      "description": "The hexadecimal color the user has chosen to display sidebar backgrounds <br>        with in their Twitter UI."
    },
    "profile_text_color": {
      "type": "string",
      "description": "he hexadecimal color the user has chosen to display text with in their Twitter UI."
    },
    "profile_use_background_image": {
      "type": "boolean",
      "description": "When true, indicates the user wants their uploaded background image to be used."
    },
    "profile_image_url": {
      "type": "string",
      "description": "An explanation about the purpose of this instance."
    },
    "profile_image_url_https": {
      "type": "string",
      "description": "An explanation about the purpose of this instance."
    },
    "profile_banner_url": {
      "type": "string",
      "description": "An explanation about the purpose of this instance."
    },
    "default_profile": {
      "type": "boolean",
      "description": "When true, indicates that the user has not altered the theme or background <br>        of their user profile."
    },
    "default_profile_image": {
      "type": "boolean",
      "description": "When true, indicates that the user has not uploaded their own profile image and <br>        a default image is used instead."
    },
    "following": {
      "type": "boolean",
      "description": "Deprecated. Nullable . Perspectival . Deprecated. When true, indicates that the <br>        authenticating user is following this user. Some false negatives are possible when set to “false,” <br>        but these false negatives are increasingly being represented as “null” instead."
    },
    "follow_request_sent": {
      "type": "null",
      "description": "An explanation about the purpose of this instance."
    },
    "notifications": {
      "type": "boolean",
      "description": "Deprecated. Nullable .May incorrectly report “false” at times. Indicates whether the <br>         authenticated user has chosen to receive this user’s Tweets by SMS. "
    }
  }
}
</pre>
