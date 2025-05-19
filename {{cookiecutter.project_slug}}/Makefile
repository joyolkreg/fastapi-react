.PHONY: build
build:
	set -e; \
	docker compose pull; \
	docker compose build

.PHONY: start
start:
	docker compose up -d

.PHONY: apply
apply:
	set -e; \
	docker compose restart; \
	docker compose run --rm backend alembic upgrade head

.PHONY: setup
setup:
	set -e; \
	sleep 5s; \
	docker compose run --rm backend python3 app/initial_data.py

.PHONY: log
log:
	docker compose logs -f

.PHONY: all
all: build start apply log
