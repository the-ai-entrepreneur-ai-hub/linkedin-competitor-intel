# LinkedIn Competitor Intelligence & Content Benchmarking

The only LinkedIn competitive analysis tool on Apify. Compare 2 to 5 LinkedIn profiles side by side and get a data driven intelligence report showing who is winning, why they are winning, and exactly what you need to do to beat them.

## What You Get

Feed in post data from any 2 to 5 LinkedIn profiles and receive a complete competitive intelligence report:

**Engagement Leaderboard** ranks every profile by average engagement so you instantly see who is dominating

**Format Comparison** reveals what content format works best for each competitor. One company might crush it with video while another wins with text posts. You will know exactly what to copy and what to avoid.

**Topic Gap Analysis** is the most valuable insight. The tool finds topics your competitors talk about that you never mention. These are content opportunities you are leaving on the table.

**Posting Strategy Diff** compares frequency, consistency, best posting days, and peak hours across all profiles. Find out if you are posting too little, too much, or at the wrong times.

**Hashtag Intelligence** shows which hashtags competitors use that you do not, and which hashtags drive the most engagement across all profiles combined.

**Sentiment Comparison** reveals the emotional tone each competitor uses and whether positive or negative content drives better results for different profiles.

**Competitive Recommendations** are the actionable output. Every recommendation references a specific competitor by name with real numbers. No generic advice. Only data backed moves you can execute today.

## Who This Is For

**Marketing agencies** benchmarking client LinkedIn performance against direct competitors. Run this monthly and show clients exactly where they stand.

**Sales teams** studying prospect content strategy before reaching out. Know what topics a company cares about before the first call.

**Personal branding coaches** comparing client profiles to industry leaders. Show clients the gap between where they are and where the top performers sit.

**Content strategists** planning LinkedIn content calendars. See what works for the competition and build your strategy around real data instead of guesswork.

## Input Format

Provide an array of profiles. Each profile needs a name and an array of posts. Posts should include text, engagement metrics, posting date, content type, and hashtags.

```json
{
  "profiles": [
    {
      "name": "Your Company",
      "posts": [
        {
          "text": "We just launched our new AI product!",
          "numLikes": 100,
          "numComments": 20,
          "numShares": 5,
          "postedAt": "2026-04-01T09:00:00Z",
          "type": "text",
          "hashtags": ["#ai"]
        }
      ]
    },
    {
      "name": "Competitor A",
      "posts": [
        {
          "text": "Excited to share our latest update.",
          "numLikes": 200,
          "numComments": 40,
          "numShares": 10,
          "postedAt": "2026-04-01T10:00:00Z",
          "type": "video",
          "hashtags": ["#ai", "#growth"]
        }
      ]
    }
  ]
}
```

Minimum 2 profiles, maximum 5. Each profile can have any number of posts. More posts means better analysis.

## Output

The output is a single JSON report pushed to the dataset:

```json
{
  "reportType": "competitive-intelligence",
  "profilesAnalyzed": 3,
  "generatedAt": "2026-04-12T...",
  "leaderboard": [
    { "name": "Competitor A", "avgEngagement": 250, "rank": 1 },
    { "name": "Your Company", "avgEngagement": 158, "rank": 2 }
  ],
  "profileAnalyses": {
    "Your Company": { "engagement, timing, formats, topics, hashtags, sentiment" },
    "Competitor A": { "..." }
  },
  "comparison": {
    "engagementLeaderboard": [],
    "formatComparison": {},
    "topicGapAnalysis": {},
    "hashtagIntelligence": {},
    "postingStrategyDiff": {},
    "sentimentComparison": {}
  },
  "recommendations": [
    "Competitor A gets 1.6x your engagement. Their secret: 40% video content vs your 0%.",
    "Competitor B talks about #scaling which gets 180 avg engagement. You never mention this topic."
  ]
}
```

## Where to Get Post Data

Use any LinkedIn scraping tool that exports posts with engagement metrics. Compatible formats include output from the LinkedIn Employee Scraper, HarvestAPI, PhantomBuster, and any tool that exports numLikes, numComments, numShares, text, postedAt, and type fields.

## Pricing

$0.02 per competitive intelligence report generated (pay per event).

## Related Tools

**LinkedIn Employee Scraper** to discover who works at competitor companies and what they post about.

**LinkedIn Content Performance Analyzer** to deep dive into a single profile with detailed engagement analysis, timing optimization, and content recommendations.

## Support

Open an issue on GitHub or message George The Developer on Apify for questions and feature requests.
