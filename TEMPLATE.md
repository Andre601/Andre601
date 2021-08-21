<!-- Links -->
[purr]: https://purrbot.site
[discord]: https://discord.gg/6dazXp6
[website]: https://andre601.ch
[spigot]: https://www.spigotmc.org/resources/authors/56829/
[patreon]: https://patreon.com/andre_601
[ko-fi]: https://ko-fi.com/andre_601

<!-- SVGs -->
[star]: https://cdn.jsdelivr.net/gh/Readme-Workflows/Readme-Icons@main/icons/octicons/StarredRepository.svg
[fork]: https://cdn.jsdelivr.net/gh/Readme-Workflows/Readme-Icons@main/icons/octicons/ForkedRepository.svg

```js
// {{ TEMPLATE: }}
module.exports = {
  MOST_STARRED: {
    type: 'customQuery',
    loop: true,
    query: async (octokit, moment, user) => {
      // You can do anything  you want with the GitHub API here.
      const result = await octokit.graphql(`
        query { 
          organization(login: "purrbot-site") {
            repositories(first: 3, isFork: false, privacy: PUBLIC, ownerAffiliations: [OWNER], orderBy: { field: STARGAZERS, direction: DESC } ) {
              edges {
                node {
                  name
                  url
                  stargazers { totalCount }
                  forks { totalCount }
                }
              }
            }
          }
        }
      `)
      const loop = []
      const repos = result.organization.repositories.edges
      for (const repo of repos) {
        loop.push({
          REPO_FULL_NAME: repo.name
          REPO_URL: repo.url
          REPO_STARS: repo.stargazers.totalCount
          REPO_FORKS: repo.forks.totalCount
        })
      }
      return loop
    }
  }
// {{ :TEMPLATE }}
```

## 👋 Hello there!
My name is Andreas but most people just call me Andre.  
On the internet am I known as either Andre_601 or Andre601. My tag on Discord is `Andre_601#0601`.

I'm a Hobby Java-Developer who creates a lot of various projects here on GitHub from which some are more popular than others.  
I joined GitHub {{ SIGNUP_AGO }}.

If you have any questions, feel free to join my [personal Discord Server][discord]. I'm pretty much always around and have time to answer stuff.

## 📁 Projects
Here is a list of various repositories based on certain criterias.

### Most starred repositories

#### Purrbot.site
{{ loop MOST_STARRED }}
- [`{{ REPO_FULL_NAME }}`]({{ REPO_URL }}) (![star] {{ REPO_STARS }} ![fork] {{ REPO_FORKS }})
{{ end MOST_STARRED }}

#### Andre601
{{ loop 3_MOST_STARRED_REPOS }}
- [`{{ REPO_FULL_NAME }}`]({{ REPO_URL }}) (![image](https://cdn.jsdelivr.net/gh/Readme-Workflows/Readme-Icons@main/icons/octicons/StarredRepository.svg) {{ REPO_STARS }} ![image](https://cdn.jsdelivr.net/gh/Readme-Workflows/Readme-Icons@main/icons/octicons/ForkedRepository.svg) {{ REPO_FORK_COUNT }})
{{ end 3_MOST_STARRED_REPOS }}

## 📊 Statistics
<img height="195px" src="https://github-readme-stats.vercel.app/api?username=Andre601&show_icons=true&hide_rank=true&title_color=3498db&bg_color=ffffff00&text_color=718096&disable_animations=true"><img height="195px" src="https://github-readme-stats.vercel.app/api/top-langs?username=Andre601&layout=compact&title_color=3498db&bg_color=ffffff00&text_color=718096">

### 📜 Recent Activity
This is a list of my 10 most recent activities on GitHub.  
The list is updates twice a day and includes opening and closing issues and opening, closing and merging Pull requests.

<!--RECENT_ACTIVITY:last_update-->
Last update: `21.08.2021 23:43:47 GMT+0200`
<!--RECENT_ACTIVITY:last_update_end-->
<!--RECENT_ACTIVITY:start-->
1. {octicons/prMerged} **Pull request merged:** [Andre601/Andre601#10](https://github.com/Andre601/Andre601/pull/10)
2. {octicons/prOpened} **Pull request opened:** [Andre601/Andre601#10](https://github.com/Andre601/Andre601/pull/10)
3. {octicons/issueOpened} **Issue opened:** [widgetbot-io/embed#190](https://github.com/widgetbot-io/embed/issues/190)
4. {octicons/prMerged} **Pull request merged:** [purrbot-site/PurrBot#424](https://github.com/purrbot-site/PurrBot/pull/424)
5. {octicons/prMerged} **Pull request merged:** [purrbot-site/PurrBot#423](https://github.com/purrbot-site/PurrBot/pull/423)
6. {octicons/prMerged} **Pull request merged:** [purrbot-site/PurrBot#422](https://github.com/purrbot-site/PurrBot/pull/422)
7. {octicons/issueOpened} **Issue opened:** [CodeCrafter47/TabOverlayCommon#5](https://github.com/CodeCrafter47/TabOverlayCommon/issues/5)
8. {octicons/prMerged} **Pull request merged:** [Andre601/OneVersionRemake#94](https://github.com/Andre601/OneVersionRemake/pull/94)
9. {octicons/prMerged} **Pull request merged:** [Andre601/OneVersionRemake#95](https://github.com/Andre601/OneVersionRemake/pull/95)
10. {octicons/prMerged} **Pull request merged:** [Andre601/OneVersionRemake#93](https://github.com/Andre601/OneVersionRemake/pull/93)
<!--RECENT_ACTIVITY:end-->

## 🔗 Links
- [Website]
- [Spigot Page][spigot]
- [Patreon]
- [Ko-fi]
