# my-one-click-shop
No-code MERN e-commerce deploy cheat-sheet

## 1. Get the code
Press ► Code → Download ZIP → unzip to Desktop → folder **myshop**

## 2. Put secrets
Inside **myshop/server** create file **`.env`** and paste:
MONGO_URI=xxx
JWT_SECRET=anyrandomphrase
STRIPE_KEY=sk_test_xxx
STRIPE_ENDPOINT_SECRET=whsec_xxx
CLIENT_URL=https://xxx.vercel.app
CLOUD_NAME=xxx
CLOUD_API_KEY=xxx
CLOUD_API_SECRET=xxx

## 3. Keys quick-grab
- Mongo: https://account.mongodb.com → Database → Connect → copy connection string
- Cloudinary: Dashboard → copy cloud_name, api_key, api_secret
- Stripe: https://dashboard.stripe.com/test → Developers → API keys → Secret key
- (Webhook secret added later)

## 4. Push to GitHub
GitHub Desktop → Add local repo → choose **myshop** folder → Publish

## 5. Deploy backend
https://render.com → New Web Service → pick repo → Root Directory = server → paste .env contents → Deploy → copy live URL

## 6. Deploy frontend
https://vercel.com → New → import repo → Root = client → add 2 env vars:
REACT_APP_API=https://xxx.onrender.com/api
REACT_APP_STRIPE_PK=pk_test_xxx
→ Deploy → get your shop URL

## 7. Finish webhook
Stripe → Webhooks → add endpoint: https://xxx.onrender.com/api/orders/webhook → event checkout.session.completed → copy signing secret → paste into Render env → redeploy

Enjoy your live shop!
