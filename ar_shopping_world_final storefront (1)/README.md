# AR Shopping World — Python Backend

Red-themed Flask + SQLite e-commerce application. It retains the original visual direction and adds Shoes, numeric shoe sizes, word-based apparel sizes, ratings, English reviews, eBay price-check links, USD/EUR display preferences, and English/Urdu/Arabic language preferences.

## Run locally

```powershell
py -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install -r requirements.txt
python app.py
```

Open `http://127.0.0.1:5000`. The SQLite database is created and seeded automatically on first launch.

## Backend functions

- Persistent SQLite product catalog, customer reviews, contact messages, seller listings, and completed orders.
- Session-backed shopping cart, payment-method selection, delivery-country rules, and checkout validation.
- Germany delivery is free for orders of two or more products worth over USD 40; otherwise standard Germany or international delivery charges apply.
- Pay on delivery and bank transfer are operational. Stripe, PayPal, and eBay checkout require the merchant's own approved credentials before activation.
- `GET /api/products` JSON product endpoint.
- All form posts are validated server-side. Set a strong `SECRET_KEY` environment variable before deployment.

For a production launch, use a production WSGI server, HTTPS, payment provider, authenticated admin area, email delivery, and move the secret key/database to managed services.

## Admin dashboard

Open `http://127.0.0.1:5000/admin/login` to manage products, stock, image uploads, orders, reviews, contact messages, and seller listings.

The initial local credentials are `admin` / `ChangeMe123!`. Before any deployment, set secure `ADMIN_USERNAME`, `ADMIN_PASSWORD`, and `SECRET_KEY` environment variables; do not use the initial password on a public server.
