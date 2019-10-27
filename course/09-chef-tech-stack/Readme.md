# Chef tech stack

# Load balancer
- Nginx

# Data Store
- Postgres

# Bookshelf
- To store all the files, data, cookbooks, etc.

# Cookbooks
- In the form of cheksum (so duplicates will be avoided)

# Messaging Queue
- Rabbitmq [all items queued up here]
- Chef-expander [ this is used to pull those message]
- Chef-solr [ exposes restapi for indexing and searching]