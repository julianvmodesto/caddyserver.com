---
title: status
type: docs
directive: true
---

status writes a status code to the response. It does not write a response body.

### Syntax

<code class="block"><span class="hl-directive">status</span> <span class="hl-arg"><i>code path</i></span></code>

*   **code** is the HTTP status code to respond with (must be numeric).
*   **path** is the base request path to match.

If you have a lot of status rewrites to group, share a status code by making a table:

<code class="block"><span class="hl-directive">status</span> <span class="hl-arg"><i>code</i></span> {
	<span class="hl-subdirective"><i>path</i></span>
}
</code>

Each line describes a base path which should have that status code written.


### Examples

For a catch-all status:

<code class="block"><span class="hl-directive">status</span> <span class="hl-arg">404 /</span></code>

To hide the existence of a secret folder:

<code class="block"><span class="hl-directive">status</span> <span class="hl-arg">404 /secrets</span></code>

To hide the existence of multiple folders:

<code class="block"><span class="hl-directive">status</span> <span class="hl-arg">404</span> {
	<span class="hl-subdirective">/hidden</span>
	<span class="hl-subdirective">/secrets</span>
}</code>
