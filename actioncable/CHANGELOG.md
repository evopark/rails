*   Support redis-rb 4.0.

    *Jeremy Daer*

*   Hash long stream identifiers when using PostgreSQL adapter.

    PostgreSQL has a limit on identifiers length (63 chars, [docs](https://www.postgresql.org/docs/current/static/sql-syntax-lexical.html#SQL-SYNTAX-IDENTIFIERS)).
    Provided fix minifies identifiers longer than 63 chars by hashing them with SHA1.

    Fixes #28751.

    *Vladimir Dementyev*

*   Action Cable's `redis` adapter allows for other common redis-rb options (`host`, `port`, `db`, `password`) in cable.yml.

    Previously, it accepts only a [redis:// url](https://www.iana.org/assignments/uri-schemes/prov/redis) as an option.
    While we can add all of these options to the `url` itself, it is not explicitly documented. This alternative setup
    is shown as the first example in the [Redis rubygem](https://github.com/redis/redis-rb#getting-started), which
    makes this set of options as sensible as using just the `url`.

    *Marc Rendl Ignacio*

## Rails 5.1.4 (September 07, 2017) ##

*   No changes.


## Rails 5.1.4.rc1 (August 24, 2017) ##

*   No changes.


## Rails 5.1.3 (August 03, 2017) ##

*   No changes.


## Rails 5.1.3.rc3 (July 31, 2017) ##

*   No changes.


## Rails 5.1.3.rc2 (July 25, 2017) ##

*   No changes.


## Rails 5.1.3.rc1 (July 19, 2017) ##

*   No changes.


## Rails 5.1.2 (June 26, 2017) ##

*   No changes.


## Rails 5.1.1 (May 12, 2017) ##

*   No changes.


## Rails 5.1.0 (April 27, 2017) ##

*   ActionCable socket errors are now logged to the console

    Previously any socket errors were ignored and this made it hard to diagnose socket issues (e.g. as discussed in #28362).

    *Edward Poot*

*   Redis subscription adapters now support `channel_prefix` option in `cable.yml`

    Avoids channel name collisions when multiple apps use the same Redis server.

    *Chad Ingram*

*   Permit same-origin connections by default.

    Added new option `config.action_cable.allow_same_origin_as_host = false`
    to disable this behaviour.

    *Dávid Halász*, *Matthew Draper*

*   Prevent race where the client could receive and act upon a
    subscription confirmation before the channel's `subscribed` method
    completed.

    Fixes #25381.

    *Vladimir Dementyev*

*   Buffer now writes to WebSocket connections, to avoid blocking threads
    that could be doing more useful things.

    *Matthew Draper*, *Tinco Andringa*

*   Protect against concurrent writes to a WebSocket connection from
    multiple threads; the underlying OS write is not always threadsafe.

    *Tinco Andringa*

*   Add `ActiveSupport::Notifications` hook to `Broadcaster#broadcast`.

    *Matthew Wear*

*   Close hijacked socket when connection is shut down.

    Fixes #25613.

    *Tinco Andringa*


Please check [5-0-stable](https://github.com/rails/rails/blob/5-0-stable/actioncable/CHANGELOG.md) for previous changes.
