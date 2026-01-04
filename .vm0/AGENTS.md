# Agent Instructions

Tasks 1, 2, and 3 should be run in parallel (in separate subagents).

First, generate a NEWS_ID (randomly generated), which will be used as the root folder for subsequent tasks, e.g., ./{NEWS_ID} directory

The browser's wss is in the CDP_WSS environment variable, need to pass $CF_ACCESS_CLIENT_ID $CF_ACCESS_CLIENT_SECRET

Use firecrawl instead of webfetch

### Task 1, complete this part in a subagent, at the end do not report all information, just report the local file paths

* Log in to rednote
* Download the first 30 notes from the homepage and place them in the rednote directory for analysis, then refresh back to the homepage and repeat twice, getting a total of 90 notes
* For the image content in notes and video cover screenshots, use multimodal capability to read the images and write the analysis to local files

### Task 2, complete this part in a subagent, at the end do not report all information, just report the local file paths

* Use the hackernews skill to download the top 30 news items to the hackernews directory, including some comments
* For the GitHub repositories and products mentioned in these news, do a secondary search and capture some information to local, also in the hackernews directory, learn as much as possible about these contents

### Task 3, complete this part in a subagent, at the end do not report all information, just report the local file paths

* Use the X (Twitter) skill to fetch the top 30 tweets from the user's timeline

### Task 4

* Use GH_TOKEN and gh to clone the e7h4n/infodb repository
* Summarize all captured posts, focusing on the following information:
  1. Overseas tech products, AI-related products
  2. Technology, AI, workflows, Claude Code, and related content
  3. GitHub repositories
  4. Original external article titles, links, tech experts, VC, and partner names mentioned
  5. Various funding-related news
* For captured products, place them in the products directory of this repository. If a related product already exists, merge with existing information
* For captured people/organizations, place them in the people directory of this repository. If a related directory already exists, merge with existing information
* For all captured information (including from rednote and hackernews), write an article in the news directory of the repository. First list the outline

```bash
# title

## Product or GitHub Repo

Name
URL
Last round of funding or Stars
Description
Media evaluation, why are people discussing this
Related news links

## Person / Organization

Original Name
Alias (if any)
Current industry/company
Description
Why are people mentioning them
Related news links

## AI-related Practice Sharing

What problem are they solving
How are they solving it
What is the value to users
How is it better than the old approach
Related news links
```

* Then for each section, expand based on the captured information, keeping the original links
* Commit & push this repository
