

```html
{% fetchxml products %}
  <fetch>
    <entity name="ponnf_product">
      <all-attributes />
    </entity>
  </fetch>
{% endfetchxml %}

<p> fetched {{ products.results.entities | size }} products.</p>

{% assign customProducts = '' | split: ',' %} <!-- Initialize an empty array -->

{% for item in products.results.entities %}
  {% assign customProduct = hash %}
  {% assign customProduct['id'] = item.productid %}
  {% assign customProduct['name'] = item.name %}
  {% assign customProducts = customProducts | push: customProduct %}
{% endfor %}


<ul>
  {% for product in products.results.entities %} 
  <div class="panel panel-default" style="box-shadow: 0 0 10px rgba(0,0,0,0.5);">
    <div class="panel-body">
      <h3>{{ product.name }}</h3>
      <p>Stock: {{ product.stock > 0 ? product.stock : 'Out of stock' }}</p>
      <p>Tags: {{ product.tags }}</p>
    </div>
  </div>
  {%- endfor -%}
</ul>



```