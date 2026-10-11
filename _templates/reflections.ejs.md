```{=html}
<% const ribbons = ["node-one", "node-two", "node-three", "node-four", "node-five"]; %>
<div class="list node-grid d-flex flex-column">
<% items.forEach((item, index) => { %>
  <article class="node-card <%- ribbons[index % ribbons.length] %> position-relative"
           <%= metadataAttrs(item) %>>
    <div class="d-flex flex-column flex-md-row gap-4 align-items-start">
      <div class="flex-grow-1">
        <h3 class="listing-title no-anchor" id="reflection-title-<%- index %>"><%- item.title %></h3>
<% if (item.date) { %>
        <p class="listing-date small text-muted"><%- item.date %></p>
<% } %>
<% if (item.description) { %>
        <p class="listing-description mb-0"><%- item.description %></p>
<% } %>
<% if (item.categories && item.categories.length) { %>
        <div class="topic-tags listing-categories mb-3">
<% item.categories.forEach(category => { %>
          <span class="topic-tag"><%- category %></span>
<% }); %>
        </div>
<% } %>
        <p class="mt-3 mb-0"><a class="stretched-link" href="<%- item.path %>" aria-labelledby="reflection-title-<%- index %>">Read reflection →</a></p>
      </div>
<% if (item.image) { %>
      <figure class="m-0 flex-shrink-0">
        <img src="<%- item.image %>" alt="<%- item['image-alt'] || '' %>"
             width="180" class="img-fluid" loading="lazy">
<% if (item['image-credit'] && item['image-source'] && item['image-license-url']) { %>
        <figcaption class="small text-muted mt-1">
          Image: <a class="position-relative z-2" href="<%- item['image-source'] %>"><%- item['image-credit'] %></a><br>
          <a class="position-relative z-2" href="<%- item['image-license-url'] %>"><%- item['image-license'] %></a>
        </figcaption>
<% } %>
      </figure>
<% } %>
    </div>
  </article>
<% }); %>
</div>
```
