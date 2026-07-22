cargo build --release

# sqlx `query!` macros need a schema to compile against: either the gitignored
# offline cache (presage-store-sqlite/.sqlx) or a live DATABASE_URL. CI builds a
# throwaway DB from the migrations (see .github/workflows/build.yml). Locally,
# refresh the offline cache after changing SQL queries or migrations with:
#
#   export DATABASE_URL="sqlite:/tmp/presage-dev.db3?mode=rwc"
#   sqlx migrate run --source presage-store-sqlite/migrations
#   (cd presage-store-sqlite && cargo sqlx prepare -- --lib)
