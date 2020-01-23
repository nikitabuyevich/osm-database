![Logo of OSM](./logo.png)

# Old School Maple's Database &middot; [![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg?style=flat-square)](./LICENSE)

> This project was originally created as part of Old School Maple (OSM), an Old School MapleStory private server which aimed to provide the most authentic and nostalgic GMS circa 2005-2007 MapleStory experience.

This MySQL dump contains the latest backup of when OSM officially shut down on September 30th, 2019.

Using this data, anyone can recreate all the accounts, characters, items, etc. of Old School Maple.

Any personally identifiable information has been stripped.

**If you're serious about migrating this data, contact [asdf.asdf.dev@gmail.com](mailto:asdf.asdf.dev@gmail.com) to request the original [BCrypted](https://en.wikipedia.org/wiki/Bcrypt) hashed passwords.**

## Notes

- Importing this data will create three new schemas: `osm`, `osmwebsite`, and `discord`.
- The `account_cs_transactions` table under the `osm` schema is grouped by `accountid` and summed on the `amount` and the `cashtype` to retrieve the available cash type for an account.
- Many of these schemas and tables are referenced in other OSM projects. [Click here to view a full list of MapleStory projects that involve this database](http://github.com/nikitabuyevich/maplestory-projects).
- This SQL structure is based off of Odin. A lot of SQL standards are subpar because of this.
- A lot of game specific tables have been dropped as they were not relevant.
- The `monster_drops`, `monster_quest_drops`, and `reactor_drops` tables in the `osm` schema are based off of the v53 BMS leak (Meaning the drops are GMS-like). Some changes have been made however:
  - Scroll drop rates have been doubled from their original values.
  - Generic equips and potions drops from mobs level 1 to 17 have been doubled from their original values.
  - Some new drops have been added by using [wayback.hidden-street.net](http://wayback.hidden-street.net/) and comparing the drops to the original ones. They've been added to best resemble what the drop rates would have been like.
  - Check out [OSM's Generic Parser](https://github.com/nikitabuyevich/osm-generic-parser) to view the exact drop table changes that were made.

## Getting Started

Simply import the [osm_data.sql.gz](./osm_data.sql.gz) file into your own MySQL instance. You can reference the [WvsGlobal Merge Parser](http://gitlab.com/nikitabuyevich/wvsglobal-merge-parser) project to get an idea on how to merge this data into your own server.

### Prerequisites

- [MySQL - v5.7.x](https://www.mysql.com/) - A relational database management system.

## Authors

- **OdinMS Creators** - _Initial work and most of the game table structures_
- **Nikita Buyevich** _(Roar / asdf)_ - _`discord` and `osmwebsite` schema's as well as some additional tables and columns_ - [nikitabuyevich](https://github.com/nikitabuyevich)

## License

This project is licensed under the MIT License - see the [LICENSE](./LICENSE) file for details.
