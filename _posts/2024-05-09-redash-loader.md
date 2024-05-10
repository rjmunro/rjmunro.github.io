---
layout: post
title: Redash Loader
---
Redash is a versatile data analytics tool that connects to various data sources, enabling users to
query them and create dashboards. With SQL knowledge, it offers flexibility for ad-hoc queries.
However, as a developer using it for larger projects, I found Redash challenging to use out of the
box.

All query and dashboard configurations are stored in the Redash database. Besides taking a complete
database backup, there's no official method for saving them. This limitation means you can't, for
example, develop a query on a staging site and seamlessly transfer it to the production server. If
you want to manage multiple Redash instances, such as for different customer databases there's no
way to update queries across them all, except manually copying the settings in the web UI.

Redash Loader uses the Redash API to download queries and dashboards, enabling you to re-upload them
to the same or a different Redash instance for updating or copying queries between instances. It
employs plain text formats - YAML for dashboards and query metadata, and native formats (e.g., SQL)
for the queries themselves. These files can be committed to Git or any other source control system
to track changes over time. They are mostly human-readable and editable directly.

The code should be considered beta quality - it was written for a specific Redash setup and has only
been tested on its ability to download and recreate that setup. It may encounter issues with Redash
features that haven't been tested extensively, but it covers the basics.

[Visit the project on Github](https://github.com/rjmunro/redash-loader).