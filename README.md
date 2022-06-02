# API Builder Project Readme

A sentiment analysis natural language processing API example based on API Builder. The API leverages [AWS Comprehend](https://aws.amazon.com/comprehend/).

The API is an example of an API First API designed in Stoplight and Built in API Builder as described in the following blog post:

* [An “API First” sentiment analysis API using API Builder](https://gist.github.com/lbrenman/4caca78903cdf1b23251e51868e300dd)

The API is shown below:

`GET /detectSentiment?text=this%20is%20great`

and accepts the text to be analyzed as query parameter, "text".

It returns the sentiment of the text:

```
{
  "Sentiment": "POSITIVE",
  "SentimentScore": {
    "Positive": 0.9985805749893188,
    "Negative": 0.00013431961997412145,
    "Neutral": 0.0008679831516928971,
    "Mixed": 0.00041714494000189006
  }
}
```

The API uses API Key authentication that is passed in a header with key apikey.

The container requires three env vars:

* API_KEY - a randomly selected API Key that you can provide that is used to authenticate API calls in a header with key apikey
* AWS_ACCESS_KEY_ID - AWS Access Key
* AWS_SECRET_ACCESS_KEY - AWS Secret Key

You can read about AWS credentials [here](https://docs.aws.amazon.com/sdk-for-javascript/v2/developer-guide/loading-node-credentials-environment.html).

A docker image can be accessed [here](https://hub.docker.com/r/lbrenman/apib_detectsentiment)
