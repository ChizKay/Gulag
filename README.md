# GULAG

Gulag is an E-commerce site built using Django. This project was highly inspired by the Project - Boutique Ado, most of the code and overall structure of the site was derived from that particular project. So kudos to the Code Institute team for creating a very detailed and professional looking project. 
Due a time constraint, I had to work on the project while learning the new material (Boutique Ado project), so I built my own project around it.
This a link to the site [https://chizkay-gulag.herokuapp.com/](Gulag)

## Technologies Used

* Django 3.1.3
* Bootstrap 4
* CSS3
* HTML
* FontAwesome
* Stripe
* JQuery
* Google fonts

## Set up

Development was all done on Gitpod. Using the provided [gitpod-full-template](https://github.com/Code-Institute-Org/gitpod-full-template) by code institute to set up the environment. Clicking on the **Use this template** button in the repository will initiate a new github repo, after creating one with a username of your choice, clicking on the **gitpod** will take you to the gitpod online IDE. Make sure gitpod is downloaded on the browser, inorder for this to work. A workspace should be available to you now.
In the terminal:
```bash
pip3 install django
```

## UX

I tried to keep things as simple as posiible, mostly using bootstrap classes to customize the site to minimise the use of custom styles. I used the Boutique ado project as a template for the overall structure with a number of tweaks. Most noticeably the header, buttons, forms, layout. 

### Pages/apps

#### home
 Large devices:

  Landing page with a background image taken from [https://www.google.com/imgres?imgurl=https://img.sdcexec.com/files/base/acbm/sdce/image/2020/10/GettyImages_961335672_ecommerce.5f7f22bc84360.png?auto%3Dformat%252Ccompress%26q%3D70&imgrefurl=https://www.sdcexec.com/software-technology/press-release/21197293/geodis-new-research-by-geodis-and-accenture-interactive-reveals-ecommerce-challenges-facing-global-brands&tbnid=Yi8-M9MQvrMwvM&vet=1&docid=SHiS25Rcy2yEkM&w=1920&h=836&itg=1&hl=en-US&source=sh/x/im](e-commerce background images), a SHOP NOW button in the center that takes you to the Products page. The   main header at the very top consisting of the main-page logo (clicking it takes you to the home page.), a search bar fixed centrally, two  links aligned to the right,         depending on if the user is authenticated. All logged in users will have a **My account** link that redirects to the user's Profile, with a **Logout** button beside it in     case the user decides to logout. Users that aren't authenticated will alternatively have a login link and **signup** button. 
  Below sits the main nav menu that contains all the product categories and sorting, and on the far end we have the Cart icon. Header is present on every page of the store,     fixed at the top.

 Medium - small devices:

  Here the header links sit at the top **My Account** is a dropdown that provides the authentication links, with the main nav links wrapped in a collapsible menu.


#### products

Displays all products in the store. Sorting on products in an input box floating on the right. Product fields include an image, rating, size if available product name and price. Clicking the product image shows a detailed view of the product on the product detail page. 

#### product detail

Shows the product details that includes the description, buttons to adjust the quantity/size of the selected the product, a submit botton to add the product to your cart. And nice message toast that pops up when an action is performed.


#### cart

Shows products added to cart. Buttons to delete and ajust quantity or size of product where applicable. Subtotal, delivery fee and Grand total.

#### checkout

Form to that takes in personal details for shipping and account details, stripe api for payments implemented. Option to save personalt details on check out, through the checkout box.


#### login/logout/signup

A confirmation email is sent to users that register for the first time. Allauth generated forms.

#### Profile
For users that have an account with the store. Shows order history and stored personal details for shipping.
     
## User Stories

### Shopper
As a user that is not logged in:

* Should be able to view all products.
* Should be able to search for products.
* Should be able to sort products by alphabetical order, size, price, rating and catergory.
* Should be able to add, edit and (delete) products to(from) cart.
* Should be able to checkout and pay for products.
* Should be able to register a new account or login.

As a user that is logged in:

* Should be able to view all products.
* Should be able to search for products.
* Should be able to sort products by alphabetical order, size, price, rating and catergory.
* Should be able to add, edit and (delete) products to(from) cart.
* Should be able to checkout and pay for products.
* Should be able to view profile (to view an order history and save their personal details).
* Should be able to login and logout.

### As a store owner:

* Should be able to (add, edit) and delete products from (to)store
      
## Testing
- Using Chrome dev tools, i tested the site in terms of its responsiveness in each device size, ranging from x-large to smallest. All buttons are functionable, and the overall   site looks good with elements properly aligned. Also tested on 3 devices (very limited because of the lockdown). Two smart phones (OnePlus 7 & Redmi 2) and a laptop (HP Pavilion). Also tested the site on Opera browser, and i had no issues there.
- Stripe payments fully functional using the card number 4242 4242 4242 4242 with any date in the future, any 3 digit cvv and any 5 digit postal code. Throws an error message when any one of the fields aren't entered correctly.
- Search bar provides a quick way to search, submitting an empty form will throw an error.
- Signing up, a verification email, sent to the new user's email address with a link to confirm the new account. Following the link takes you to the sign in page. Which will then take the user to the home page.

## Naming Scheme
* HTML/CSS: using dashes, eg. form-submit
* Javascript: camelcase, eg. stripePublicKey
* Python: underscores. eg. stripe_public_key

## Requirements.txt
```
asgiref==3.3.0
boto3==1.16.25
botocore==1.19.25
dj-database-url==0.5.0
Django==3.1.3
django-allauth==0.43.0
django-countries==6.1.3
django-crispy-forms==1.10.0
django-storages==1.10.1
gunicorn==20.0.4
jmespath==0.10.0
oauthlib==3.1.0
Pillow==8.0.1
psycopg2-binary==2.8.6
PyJWT==1.7.1
python3-openid==3.2.0
pytz==2020.4
requests-oauthlib==1.3.0
s3transfer==0.3.3
sqlparse==0.4.1
stripe==2.55.0

```
 
 ## Deployment
 
 1. login to heroku through the terminal using:
  ```bash
heroku login -i
```
  Alternatively you can use:
  ```bash
heroku login
```
  But I was getting an error on the preview page when i tried to login
  2. Create a new Heroku App.
  3. In the Heroku App Dashboard, under the Resources tab, add Heroku Postgres and select the "Hobby Dev - Free" option.
  4. Install dj_database_url using:
  ```bash
pip3 install dj-database-url
``` 
  5. Install psycopg2-binary using:
  ```bash
pip3 install psycopg2-binary
```
  6. pip3 freeze > requirements.txt
  7. import dj_database_url to settings.py
  8. In settings.py add the following code:
  ```bash
    if 'DATABASE_URL' in os.environ:
    DATABASES = {
        'default': dj_database_url.parse(os.environ.get('DATABASE_URL'))
    }
  else:
    DATABASES = {
        'default': {
            'ENGINE': 'django.db.backends.sqlite3',
            'NAME': os.path.join(BASE_DIR, 'db.sqlite3'),
         }
  ```
  9. Run:
 ```bash
python3 manage.py migrate
python3 manage.py createsuperuser
git add . 
git commit.....
```
  10. In settings.py add the following code, since it's advised to set DEBUG to false in production, this will ensure it remains that way.
   ```bash
  DEBUG = 'DEVELOPMENT' in os.environ
  ```
  11. In heroku add a DISABLE_COLLECTSTATIC Config Var and set its value to 1. So heroku wil not start collecting static files.
  12. Install gunicorn with ```pip3 install gunicorn``` and then ```pip3 freeze > requirements
  13. Create a Procfile in the main dir and insert ```web: gunicorn the_woodworks.wsgi:application 
  14. In settings.py set ```ALLOWED_HOSTS = ['appname.herokuapp.com', 'localhost']
  15. commit to git and push to heroku with:
  ```
    heroku git:remote -a appname
    git push heroku master
  ```
  16. To top it all off, there are several variables and secret keys that need to be set in the heroku app and should all be present in your settings.py. Here's a list of the       ones in my app:
    ```
    STRIPE_PUBLIC_KEY
    STRIPE_SECRET_KEY
    STRIPE_WH_SECRET
    SECRET_KEY
    AWS_ACCESS_KEY_ID
    AWS_SECRET_ACCESS_KEY
    EMAIL_HOST_USER
    EMAIL_HOST_PASS
    DATABASE_URL
    DISABLE_COLLECTSTATIC
    USE_AWS
   ```

## Acknowledgement

Because of the limited time i had to get the project done, most of the code was taken from the Boutique ado project, in particular the views, models, html, css javascript, fixtures and images. I tried to search for datasets on https://www.kaggle.com/datasets, but I couldn't find any that were suitable. Alternatively i could've just added products through the admin panel but that would have been time consuming.
Big shout out to the slack community and my mentor Sandeep, they always seem to come through when I have roadblocks. 

