Version 0.1.0 alpha
-----------------------------------------------------------------------------------------------------------------------
    * Created elasticsearch attribute group
    * Name suggest and weight attributes

Version 0.2.0
-----------------------------------------------------------------------------------------------------------------------
    * Created 'add_categories_to_name_suggest' attribute

Version 0.3.0 alpha
-----------------------------------------------------------------------------------------------------------------------
    * Created Pocketphp_Elasticsearch_Autoloader (could not load Elasticsearch from lib)
    * Created lib/Pocketphp namespace
    * Added Elasticsearch library with dependencies (Guzzle, Monolog, Psr, Symfony, Pimple)
    * Replaced Zend_Http_Client and Cluster Manager with \Elasticsearch\Client
    * Implemented Suggester with Elasticsearch lib
    * Implemented fuzzy suggest query - added setting in system config

Version 0.4.0 alpha
-----------------------------------------------------------------------------------------------------------------------
    * createRemoveCategoryNamesSuggestestionsAttribute replaces createAddCategoriesToNameSuggestAttribute
    * Created "remove_catnames_suggestions" and "remove_name_suggestions"
    * Moved lib to module namespace (edited Autoloader)
    * Refactored _prepareNameSuggestField
    * Replaced foreach loop with collection walk when indexing product collection
    * Added additional host system config textarea allowing for multiple connections

Version 0.5.0 alpha
-----------------------------------------------------------------------------------------------------------------------
    * searches (layered navigation collection)
    * implemented layered category, price and attribute filter (missing decimal)
    * added Engine type

Version 0.6.0 alpha
-----------------------------------------------------------------------------------------------------------------------
    * major refactoring of category, price and attribute filters
    * created es_analyzed_fields attribute (deprecated)
    * improvement to mapping and indexing process: analyzer and type for each attribute in a store
    * completed catalog filters for layered navigation
    * added query dsl classes
    * added replicas and number of shards to config
    * set from and size in dsl query
    * implemented layered navigation for category views


Version 0.7.0 alpha
-----------------------------------------------------------------------------------------------------------------------
    * added short description to name_suggest
    * improved indexing process and implemented updating docs when product is saved
    * added jetty plugin for authentication:
        * installed jetty with bin/plugin -url https://oss-es-plugins.s3.amazonaws.com/elasticsearch-jetty/elasticsearch-jetty-1.1.0-beta.zip -install elasticsearch-jetty-1.1.0-beta
        * created config/realm.properties file in elasticsearch dir config
        * added http.type: com.sonian.elasticsearch.http.jetty.JettyHttpServerTransportModule to elasticsearch.yml
        * also set in elasticsearch.yml sonian.elasticsearch.http.jetty:
              config: jetty.xml,jetty-hash-auth.xml,jetty-restrict-all.xml

Version 0.7.1 alpha
-----------------------------------------------------------------------------------------------------------------------
    * fixed bug in observer: when saving a product indexed was deleted. count of product ids was wrongly removed
      from method

Version 0.8.0 alpha
-----------------------------------------------------------------------------------------------------------------------
    * implemeted searched fields as configuration setting allowing to defined searched field CSV value
    * improved bool query with fields array

Version 0.9.0 alpha
-----------------------------------------------------------------------------------------------------------------------
    * minor mapping improvement
    * integrated advanced search (layout + results)
    * added lowercase_expanded_terms (boolean type) to bool query (with getter and setter)
    * added use_dis_max (boolean type) to bool query (with getter and setter)
    * added profiler to searcher
    * refactored bool query with should and must and added query string class
    * added source queries model and functionality to define in admin the query to run. at the moment only query_string
      implemented
    * removed search fields CSV default value from config.xml. leaving default value to _all.
    * implemented fuzzy_like_this query
    * set fuzzy_like_this query fuzzyness to AUTO by default
    * set size for terms facet. with default size of 10, some facets were not returned.
      currently hard-coded in constant FACETS_TERMS_MAX_SIZE and set to 1000.
      (@see Pocketphp_Elasticsearch_Model_Query_Filtered)
    * improved performance by setting result collection total records when stats query message is sent
    * implemented Apache Lucene query text escaper following http://lucene.apache.org/core/3_6_0/queryparsersyntax.html
    * set analyzer 'standard' for name_suggest
    * added name_suggest_static field with name suggest input value
    * changed prepend to 'true' in spl_autoload_register call in Autoloader to stop PHP warning generated by Magento
      Autoloader when trying to use Elasticsearch\Client class
    * fixed all warning and notices with DEVELOPER MODE on
    * listening to adminhtml event catalog_product_delete_after_done and setting fulltext indexing to 'required'

Version 0.10.0 alpha
-----------------------------------------------------------------------------------------------------------------------
    * added translate CSV files for US and GB
    * changed license fixed comments
    * Fix duplicate engine option in Magent EE
    * Rename CHANGE_LOG to CHANGE_LOG.md

Version 0.10.1 alpha
-----------------------------------------------------------------------------------------------------------------------
    * Fix indexing on Magento EE with PHP versions higher than 5.3
    * changed code pool to 'community'

Version 0.10.2 alpha
    * Add layout and template for rwd design package (Magento 1.9.0.1)
    * Add popular search term footer link (replaces default Magento)