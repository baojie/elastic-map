## NOTE: This demo will not work until you replace `[GOOGLE_API_KEY]` in index.html with your Google API key.

### Qbox.io searchable map demo

- This demo uses a [Qbox.io](http://qbox.io) search index populated with a million records. [see it [live](http://qbox.io/demos/map)]
- Searching is performed server-side by [Elasticsearch](http://www.elasticsearch.org).
- The UI is constructed with [Google Maps](https://developers.google.com/maps/documentation/javascript/) and [Bootstrap](http://twitter.github.io/bootstrap).

### Dependencies (included)

- jQuery v1.9.1
- Bootstrap v2.3.1
- Handlebars v1.0.0-rc.3
- [bootstrap-slider.js](http://www.eyecon.ro/bootstrap-slider/)
- qbox-map.js


### To use as-is
- Just clone this repository and open index.html. :)

### To use with your elasticsearch endpoint and Google API key
Open qbox-map.js and look at the first few lines: 

```javascript
(function(){

  var ELASTICSEARCH_INDEX_ENDPOINT = 'http://api.qbox.io/mqlewrfa/people/person';
.
.
.
}
```
Replace `ELASTICSEARCH_INDEX_ENDPOINT` with your index endpoint.

You will also need to use your `GOOGLE_API_KEY` in index.html:

```html
    <script src="https://maps.googleapis.com/maps/api/js?key=[GOOGLE_API_KEY]&amp;sensor=false"></script>
```