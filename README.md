Practive Rust App for DigitalOcean

docker build --tag zero2prod --file Dockerfile .

docker run -p 8000:8000 zero2prod

doctl apps create --spec spec.yaml

doctl apps list

# You can retrieve your app id using `doctl apps list`
doctl apps update YOUR-APP-ID --spec=spec.yaml

Example: doctl apps update 4339ba1a-51b2-4d72-9af5-d08c1c4f9f20 --spec=spec.yaml

DATABASE_URL=YOUR-DIGITAL-OCEAN-DB-CONNECTION-STRING sqlx migrate run

Example: DATABASE_URL=postgresql://newsletter:AVNS_Y6pSu1SsDupzCWcuyS4@app-d5d1630c-1d27-4c39-8fae-c4182fc92a61-do-user-3594497-0.b.db.ondigitalocean.com:25060/newsletter?sslmode=require sqlx migrate run

SET DATABASE_URL="postgresql://newsletter:AVNS_NJId_CNyiEHTB9fmLcT@app-aaae15c4-2267-48c9-9ad7-bf553186684f-do-user-3594497-0.b.db.ondigitalocean.com:25060/newsletter?sslmode=require" sqlx migrate run


cargo check --all-targets