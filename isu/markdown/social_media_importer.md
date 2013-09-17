<img src="../images/IXM-Transparent-Vertical.jpg" style="float:right; margin:-10px 15px 0 0;" height="90" />
![Indiana State University logo](../images/isu_logo.png)

# [ISU-34](https://imagex.atlassian.net/browse/ISU-34) - Social Media Importer - 2013-04-03

The goal of the social media importer is to automatically retrieve content from various social media services (Facebook, Twitter, YouTube, and Pinterest) and place it in the Drupal site so that it can be used in a myriad of ways. In order to accomplish this, the social media importer extends core Drupal functionality and several prominent and well-weathered contributed modules. The social media importer includes:

- 'social' module which creates a custom social entity type
- 'facebook\_import' module which imports Facebook content
- 'youtube\_import' module which imports YouTube content
- 'pinterest\_import' module which imports Pinterest content
- 'twitter\_import' module which imports Twitter content
- 'isu\_social\_importer' feature module which contains the social types, permissions, feeds importers, and related variable settings

The social media importer relies upon:

- core entity functionality and contributed entity api
- feeds module
- feeds\_jsonpath\_parser module for parsing json using feeds
- media\_feeds and file\_entity modules for creating file entities during the feeds import
- twitter and oauth modules for handling twitter authentication

## Sections

1. [Structure](#structure)
2. [Data model](#data-model)
3. [Importers](#importers)
4. [How it all works](#how-it-all-works)


## Structure

The social media importer creates its own entity type called 'social'. An entity is a core Drupal building block. The main Drupal entity is a node. Before Drupal 7, nodes were really the only entities in Drupal. However, Drupal 7 brought with it the ability to create your own entity types in order to structure data and functionality to suite your needs. The massive benefit of creating entity types (versus building your own custom approach) is that they automatically integrate with all of the rest of Drupal components. So, but creating a social entity type, the social content is available to be integrated with views, field, features, other entities, etc.

The social entity type actually contains two entities: the actual social entity and a social type entity. This allows us to create new social types just like we would create node/content types. As a result, we're able to create a new social type for each new social media service that we'd like to store in the site. The benefit of this structure is that it makes the importer easily extendable to include additional social media services.

While the social entity stores the data and helps us integrate it with the rest of Drupal, it doesn't help get the data into Drupal to begin with. For that, the social media importer integrates with the Feeds module to create a robust way of automatically importing data from a social media service feed.

The Social module creates the baseline feeds integration by extending a feeds processor so that social entities can be created from feeds imports. The SocialProcessor retrieves the fields of the social type and allows you to map them as destinations for feeds imports.


## Data model

With the handy social entity and social type entities in place, we're able to create four new social types using the same fieldable interface as we use for content types. As a result, there is a Facebook, Twitter, YouTube, and Pinterest social type. Each social type has its own set of fields that match the data retrieved from each service's feed.

In addition to the fields configured for these social types via the admin UI, the social entity contains 3 additional fields that are common to any social type:

- A unique item id: this is a unique identifier from the service for the item being stored (the id of the twitter tweet, facebook post, youtube video, etc.). While item ids do not have to be unique in the database, they do have to be unique within their own social type.
- A created date: the date and time the item was created in Drupal.
- An updated date: the date and time the item was last updated in Drupal.


## Importers

In order to get the data into Drupal, there is a specific import module for each social media service. Depending on the data, format, and requirements for retrieving the service's feed, these modules do different things. In most cases, they extend Feeds by creating their own feeds fetchers and parsers. This allows them to use their own methods for authenticating and fetching the data from the service and then parsing the results of the feed in a way that allows us to store them in social entities and a useful way.

### Facebook Import

![Facebook fetcher](http://o7.no/YSPAST)

![Facebook parser](http://o7.no/YSPzhN)

Facebook Import creates its own feeds fetcher and parser. The fetcher uses the Facebook App credentials that must be stored on the Facebook Import configuration page.

![Facebook configuration](http://o7.no/Z1MxEJ)

With the App credentials, the fetcher retrieves an access token from Facebook (which is required to get any feed of content from Facebook), and then retrieves the actual feed using the access token.

The Facebook feed is retrieved using JSON as the feed format. Facebook Import creates its own parser which is an extension of the feeds\_jsonpath\_parser in order to parse it. As a result, the importer maps the data to the fields we have setup in the Facebook social type.

One of the really nice attributes of this approach is that it allows us to use the media\_feeds module to actually store feed data as file entities. So, when the Facebook feed contains an image url, it's stored as an image entity in the social entity.


### YouTube Import

![YouTube fetcher](http://o7.no/YSQXRy)

![YouTube parser](http://o7.no/Z1O51M)

YouTube Import creates its own feeds fetcher and parser. The fetcher mainly just allows us to use the YouTube user name to fetch the feed, rather than having to enter the actual feed url.

The YouTube parser does minimal work to extract the video id and convert the published and updated dates to a format that allows us to save them as dates in Drupal.


### Pinterest Import

Pinterest Import only creates a feeds parser. Pinterest doesn't have an official api, so in this case we're just retrieving an ordinary rss feed. The parser extracts an id, description, and image url for nicer storage in the Pinterest social type.


### Twitter Import

Twitter is the one major exception to the importer pattern. The Drupal Twitter module is really well done and contains an api that allows us to hook into it. Twitter module handles the somewhat complex Oauth authentication and authorization for us with minimal configuration. The Twitter Import module just hooks into the tweet save function in the Twitter module api. When a tweet is saved, Twitter Import looks for an existing social entity that matches the tweet and updates it, or creates a new social entity from the tweet.

To set this up, the Twitter module must be configured properly with the appropriate Twitter app credentials, and then a twitter user account must be linked to the site using the admin UI. Once that's complete and tweets are selected to be imported into the site, Twitter Import module will see them and create social entities of them.


## How it all works

Since we've created the social entity type, the admin interface can have its own separate section for social content. This is nice because this content, which is coming from outside the site, won't be intermingling with ordinary site content generated within the site.

![Social content](http://o7.no/YSRX8c)

The table of social content is a view that is packaged with the social module.  New social types can be created and existing social types can be configured using the stock Drupal field interface.

![Social types](http://o7.no/YSTeMt)

Since we have fully functional entities, they contain create, read, update, and delete (CRUD) capabilities for each social entity.

Create:

![Create Facebook](http://o7.no/Z1Sku7)

View:

![View Facebook](http://o7.no/YSTXgH)

Edit:

![Edit Facebook](http://o7.no/YSU1x0)

Delete:

![Delete Facebook](http://o7.no/YSU4sM)




