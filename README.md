# Svpply

This is a ruby wrapper for the Svpply API. It's a work in progress, and currently not recommended for production usage.

## Installation

Add this line to your application's Gemfile:

    gem 'svpply', '0.0.1'

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install svpply

## Usage

### Products

To return all products in the "Shop" section:

    $ Svpply.products

To perform a search, the syntax is similar:

    $ Svpply.products("tshirt")
    $ Svpply.products("tshirt", genders: ['male'], prices: ['$1-20'])
    $ Svpply.products(genders: ['male'])

etc...

Single product lookup:

    $ Svpply.product(880581)

Single product image permalink:

	$ Svpply.product_image_permalink(880581, 'medium')  # 450x450px (default)
    $ Svpply.product_image_permalink(880581, 'small')   # 195x195px
    $ Svpply.product_image_permalink(880581, 'large')   # 625x625px


### Categories

Return all categories:

    $ Svpply.categories

Products in a given category:

    $ Svpply.categories.first.products

Categories have children categories:

    $ Svpply.categories.first.children
    $ Svpply.categories.first.children.first.products

etc...

### Stores

Single store lookup:

    $ Svpply.store(48037)

Store products lookup:

	$ Svpply.store_products(48037)
	$ Svpply.store_products(48037, limit: 10, offset: 2)
	$ Svpply.store_products(48037, genders: ['male'], prices: ['$1-20'])

### Collections

Single collection lookup:

    $ Svpply.collection(2032)

Collection products lookup:

	$ Svpply.collection_products(2032)
	$ Svpply.collection_products(2032, limit: 10, offset: 2)

### Users

Single user lookup:

    $ Svpply.user(4058)

Collection products lookup:

	$ Svpply.user_products(4058)
	$ Svpply.user_products(4058, limit: 10, offset: 2)

## TODO:

1. Tests
2. Refactor
3. Flush out full API

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Added some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
