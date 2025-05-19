
.PHONY: start
start:
	docker compose up -d

.PHONY: build
build:
	set -e; \
	docker compose pull; \
	docker compose build

apply: apply
	set -e; \
	docker compose restart; \
	docker compose run --rm backend alembic upgrade head

.PHONY: initialize
initialize:
	set -e; \
	sleep 5s; \
	docker compose run --rm backend python3 app/initial_data.py

.PHONY: log
log:
	docker compose logs -f

all: build start apply log
