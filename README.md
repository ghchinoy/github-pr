# Github PR

Determine how many PRs are open per user per project

Aaron Fullerton said he had a lot of github PRs open and was somewhat overwhelmed 05/03/2018


* Get repos `/orgs/:owner/repos`
  * should get the links response header for pagination and combine all responses
* Get pull requests per repo `/repos/:owner/:repo/pulls`
  * should be done in a goroutine
* Pulls will show assignees, but doesn't show total reviewers, that has to be compiled from, get `/repos/:owner/:repo/pulls/:number/reviews`
  * should be done in a goroutine


---

Would love to have a Github OAuth app that shows 

[ My stats - open PRs assigned to me across x number of repos ]

[ repos table that sorts number of PRs assigned to a person by repo ]

---

Then, once we have that sort of "my load / other people's load" view of PRs, more stats, which can be done on closed PRs

* how often do PRs occur
   * how often does user X make a PR
* how long does a PR stay open?
   * What user has the most comments on a PR?
* most frequently requested reviewer
* user with most comments on PRs

https://github.com/sportngin/hubstats

* developer count (users that commit PRs)
* reviewers count (users that review)
* comments count (total number of comments across all PRs)
* PRs merged count (total number of PRs merged)
* PRs per developer
* Avg Additions per PR
* Avg Deletions per PR
* Net total Additions

https://github.com/xiongchiamiov/github-pr-stats
https://github.com/interviewstreet/pr-stats
https://developer.github.com/v3/repos/statistics/
https://github.com/dazz/repo-pr-stats

--


V3 - current
```
Accept: application/vnd.github.v3+json
```

V4 - graphql, future
```
Accept: application/vnd.github.jean-grey-preview+json
```

curl -i https://api.github.com/users/octocat/orgs

OAuth Token in Heaer

```
curl -H "Authorization: token OAUTH-TOKEN" https://api.github.com
```

OAuth Key / Secret

```
curl 'https://api.github.com/users/whatever?client_id=xxxx&client_secret=yyyy'
```