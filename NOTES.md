cargo build --release

# sqlx `query!` macros compile against the committed offline cache (`.sqlx/` at
# the workspace root), so plain builds need no database. After changing SQL
# queries or migrations, regenerate the cache and commit it:
#
#   just prepare-sqlx
#
# (needs sqlx-cli; see the justfile for the underlying commands)
