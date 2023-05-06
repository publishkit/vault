---
title: Some project
tags: [projects, spoiler]
props:
  passed: false
  deadline: 17/04/2023
---

<div id="deadline-info" style="display: none;">
            <p>The portfolio will be released on April 17, 2023.</p>
        </div>
<!-- before deadline --><p data-show="!~passed"></p>
The portfolio will be released on April 17, 2023.

<!-- countdown widget --><p data-countdown data-bind="deadline"></p>
<!-- end:div --><p data-end></p>

<!-- after deadline --><p data-show="~passed"></p>
The portfolio release target date was April 17, 2023. It was missed due to <!-- icon --><i class="fab fa-gitlab" style="font-size: 0.8em; vertical-align: top; margin-right: 2px;"></i> [GitLab Hackathon preparation](https://www.linkedin.com/posts/petro-koriakin-19939b224_are-you-ready-to-level-up-your-engineering-activity-7052260916893036546-WBru?utm_source=share&amp;utm_medium=member_desktop) efforts.

<!-- end:div --><p data-end></p>
