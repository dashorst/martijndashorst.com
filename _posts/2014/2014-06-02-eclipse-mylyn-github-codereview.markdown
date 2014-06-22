---
layout: post
status: publish
published: true
title: 'Using Eclipse Mylyn for Github Pull Request Code Review'
author: Martijn Dashorst
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
date: '2014-06-02 17:20:54 +0100'
date_gmt: '2014-06-02 16:20:54 +0100'
categories:
---

At €dayjob we use github as our code repository and recently opted to
require code reviews for our contributions. The benefits of code
reviews require a separate post, so I won't discuss those in detail
here.

As code reviews are a given in our project, I thought that it would be
awesome if I can checkout a pull request using Mylyn and have the
context contain only the relevant files partaining to the pull request.

As you can imagine, a typical pull request consists of a dozen or two
files, and while reviewing them in the Github web interface is doable,
I miss navigating through the code in the web interface (ctrl-click
anyone).

So I figured Mylyn would be a solution that would help me with my
usecase. Unfortunately it doesn't. There is apparantly no way to
instruct Mylyn to checkout the branch and have all modified classes be
added to the context--or nobody has thought of such a use case.
