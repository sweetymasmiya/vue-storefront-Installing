# Vue Storefront Installing

#### 1. What is Vue Storefront ?

<p> Vue Storefront is a standalone PWA storefront for your eCommerce, able to connect with any eCommerce backend (eg. Magento, Prestashop or Shopware) through the API.</p>

#### 2. How to Install Vue Storefront Linux/MacOS ? 

###### When you want to play with Vue Storefront, there are three options:

1. You can set up the frontend connected to our demo backend platform (best for trying out Vue Storefront).
2. You can set up frontend with your own vue-storefront-api and database dumped from the demo.
3. You can set up frontend with vue-storefront-api connected to your eCommerce backend.

##### Option 3 is consider in this guidline

1. clone vue-storefront
```
git clone https://github.com/DivanteLtd/vue-storefront.git vue-storefront
cd vue-storefront
yarn
yarn installer

cp config/default.json config/local.json
```

2. clone vue-storefront-api
```
cd vue-storefront
git clone https://github.com/DivanteLtd/vue-storefront-api.git vue-storefront-api
cd vue-storefront-api
yarn install

cp config/default.json config/local.json
```
> Change magento 2 project api token and key

```
nano config/local.json

 "magento2": {
    "imgUrl": "http://demo-magento2.vuestorefront.io/media/catalog/product",
    "assetPath": "/../var/magento2-sample-data/pub/media",
    "api": {
      "url": "http://demo-magento2.vuestorefront.io/rest",
      "consumerKey": "byv3730rhoulpopcq64don8ukb8lf2gq",
      "consumerSecret": "u9q4fcobv7vfx9td80oupa6uhexc27rb",
      "accessToken": "040xx3qy7s0j28o3q0exrfop579cy20m",
      "accessTokenSecret": "7qunl3p505rubmr7u1ijt7odyialnih9"
    }
},
```

3. Magento 2 Setup

```
https://devdocs.magento.com/guides/v2.3/install-gde/system-requirements.html
https://www.mageplaza.com/kb/how-to-install-magento-2.html

```

#### Run Project

1. Go to vue-storefront-api folder

```
docker-compose up -d
yarn mage2vs import
yarn dev
```

1. Go to vue-storefront folder

```
yarn dev
```

Your vue-storefront-api : http://localhost:8080/
Your vue-storefront : http://localhost:3000/

You can also check live demo https://demo.vuestorefront.io/
