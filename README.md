# Set up
In this assignment, we explore our skills with Pymongo and NoSQL.

In both Jupyter Notebook files, I use the following dependencies:
<p> from pymongo import MongoClient </p>
<p>   from pprint import pprint. </p>
Additionally, all instances of MongoClient are created as follows:
 <p>  mongo = MongoClient(port=27017). </p>

From here, we want to explore the 'uk_food' database and the 'establishments' collection. We add an item to the collection and check we inserted it properly with the following code:
<p>  establishments.insert_one(penang_flavours) </p>
 <p> query = {'BusinessName' : "Penang Flavours"} </p>
<p>  results = establishments.find(query) </p>
<p> for result in results: </p>
 <p> pprint(result). <p>
    
We discovered some of the missing information from the insertion query using a find query and update the inserted item. Lastly, we updated the geolocation
data to decimals as they were strings intially.

# Analysis

Our analysises used the following queries: 

<p>query ={'scores.Hygiene': 20}</p>
<p>query = {'LocalAuthorityName': {'$regex' : 'London'}, 'RatingValue': {'$gte': '4' }}</p>
  
<p>query = {'RatingValue': '5',</p>
         <p>'geocode.latitude': {'$gte': latitude - degree_search , '$lte': latitude + degree_search },</p>
        <p> 'geocode.longitude': {'$gte': longitude - degree_search , '$lte': longitude + degree_search } }</p>
         
<p>match_query = {'$match': {'scores.Hygiene': 0}}</p>
<p>group_query = {'$group': {'_id': {'LocalAuthorityName':'$LocalAuthorityName'}</p>
                          'count':{'$sum':1}}}</p>
<p>sort_values = {'$sort': { 'count': -1}}</p>
