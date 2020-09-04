---
title: process_comment
parent: Tags Reference
layout: default
---

# process_comment

The **process_comment** tag is meant to be used at the successful submission of a comments form.<br/>
It simply tries to insert the submitted comment into the database. If it is successful in inserting the comment, the tag sets the *k_process_comment_success* variable otherwise it sets the *k_process_comment_error* variable in the context of its parent tag.

Please see [**Core Concepts - Comments**](../concepts/using-comments.html) for an example of this tag's usage.

## Parameters

This tag does not accept any parameters.

## Variables

This tag is self-closing and does not set any variables of its own except the *k_process_comment_success* and *k_process_comment_error* variables that it sets in the context of the calling tag to signal the result of its operation.

## Related Tags

* [comments](./comments.html)
