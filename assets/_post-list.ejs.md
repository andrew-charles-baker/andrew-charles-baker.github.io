::: {.list .post-list}

<% for (const item of items) { %>

::: {.post-row <%= metadataAttrs(item) %>}

```{=html}
<div class="post-date listing-date"><%= item.date %></div>
<div class="post-main">
<h3 class="no-anchor post-title listing-title"><a href="<%- item.path %>"><%= item.title %></a></h3>
```

<% if (item.subtitle) { %>

```{=html}
<p class="post-blurb listing-subtitle"><%= item.subtitle %></p>
```

<% } else if (item.description) { %>

```{=html}
<div class="post-blurb listing-description">
```

<%= item.description %>

```{=html}
</div>
```

<% } %>

<% if (item.categories) { %>

```{=html}
<div class="post-cats listing-categories">
<% for (const category of item.categories) { %>
<a href="#" class="post-cat listing-category" onclick="window.quartoListingCategory('<%= utils.b64encode(category) %>'); return false;"><%= category %></a>
<% } %>
</div>
```

<% } %>

```{=html}
</div>
```

:::

<% } %>

:::
