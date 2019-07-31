# Syllable Razzle Strapi API

> In this application you will see how to

- Create custom routes / controllers / services.
- Use groups and authentication permissions

# Setup

**1 —** Clone the repository.

```bash
git clone git@github.com:syllable-hq/syllable-razzle-strapi-api.git
```

**2 —** Install and run MYSQL.

## API

**3 —** Go to the `backend` folder, install the dependencies and start API.

```bash
cd backend
npm install && npm start
# It take few minutes
```

**4 —** Update permissions.

You have to go in your admin panel and update permission of the `Authenticated` role (Plugins > Users & Permissions > Authenticated).

## Bootstrap application data

When you start your application for the first time, if you don't have any data, we auto inject a dataset in your mongo database.
You can see how we did it in the `/config/function/bootstrap.js` file. It calls the `initDatabase` function of the `/api/app/service/App.js` service's file. The dataset is in `/api/app/config/data.json`.

## Custom route

To apply the logged user as the author of the review we have to custom the back-e,d part, we created a `/reviews/submit` route.
In the controller function we get the user id from the session and apply the value to the review object.

## Authentication

In `public/product.html` page we add login / register function to be able to submit a review. At the end of the `/public/scripts/product.js` file you will see how use auth routes. Documentation link https://strapi.io/documentation/guides/authentification.html.

## Admin

In the admin panel (`http://localhost:1337/admin`) you will be able to manage (create/update/delete) models.
