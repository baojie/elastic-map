*NOTE: This demo will not work until you replace `[GOOGLE_API_KEY]` in index.html with your Google API key. (instructions [here](https://developers.google.com/maps/documentation/javascript/tutorial))*

### Qbox.io searchable map demo

- This demo uses a [Qbox.io](http://qbox.io) search index populated with a million records. [see it [live](http://qbox.io/demos/map)]
- Searching is performed server-side by [Elasticsearch](http://www.elasticsearch.org).
- The UI is constructed with [Google Maps](https://developers.google.com/maps/documentation/javascript/) and [Bootstrap](http://twitter.github.io/bootstrap).

### Dependencies

- jQuery v1.9.1
- Bootstrap v2.3.1
- Handlebars v1.0.0-rc.3
- [bootstrap-slider.js](http://www.eyecon.ro/bootstrap-slider/)
- Google Maps JavaScript API v3
- qbox-map.js


### To use with your elasticsearch endpoint and Google API key

First you will also need to use your `GOOGLE_API_KEY` in index.html:

```html
  <script src="https://maps.googleapis.com/maps/api/js?key=[GOOGLE_API_KEY]&amp;sensor=false"></script>
```

Getting a Google Maps API key is simple (though you will need a google account), and instructions can be found [here](https://developers.google.com/maps/documentation/javascript/tutorial).


If you want to use this code with your own elasticsearch index, open qbox-map.js and replace `ELASTICSEARCH_INDEX_ENDPOINT` with your index endpoint: 

```javascript
(function(){

  var ELASTICSEARCH_INDEX_ENDPOINT = 'http://api.qbox.io/hnbiojicnyvmqlqf/people/person';
.
.
.
```

You will probably also want to edit the handlebars template for the results (in qbox-map.js) to match the structure of your data:

```javascript
.
.
.
  var resultTemplate = Handlebars.compile('\
    <tr class="result-row" id={{id}}>\
      <td>{{first_name}}</td>\
      <td>{{last_name}}</td>\
      <td>{{email}}</td>\
      <td>{{formatted_lat}}</td>\
      <td>{{formatted_lon}}</td>\
    </tr>\
  ');
.
.
.
```