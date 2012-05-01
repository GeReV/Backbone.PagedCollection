Backbone.PagedCollection
========================

A Backbone collection with paging and simple caching capabilities

## Usage ##

`var collection = new Backbone.PagedCollection(models, [options]);`

PagedCollection accepts the same options as Backbone.Collection, with the following additions:  
***perPage***: number of items to display per page, defaults to `10`.  
***collection***: type of collection to use as the page collection, defaults to `Backbone.Collection`.

There's an optional `collection.filter()` function, which accepts an object of key-values, resets the collection and passes the filter object as the data in the `Backbone.sync` requests.

## Server-side Integration ##

PagedCollection expects server responses to be of the following format:

```js
{
  total: [total],
  per_page: [per_page],
  page: [current_page],
  items: [array_of_items]
}
```
