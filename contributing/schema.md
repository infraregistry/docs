# Schema

infraregistry uses [SurrealDB](https://surrealdb.com) for maintaining relationship graphs and Postgres for relational data.

{% hint style="info" %}
The SurrealDB schema declaration is located [here](https://github.com/infraregistry/schema/blob/main/surrealdb/product.surql).
{% endhint %}

## SurrealDB Architecture

<figure><img src="../.gitbook/assets/Figma-000818 (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Want to see how we recursively generate relationships with SurrealDB? Check out this blog post [https://matthewdavis.io/surrealdb-recursive-graph-query](https://matthewdavis.io/surrealdb-recursive-graph-query/)!
{% endhint %}

