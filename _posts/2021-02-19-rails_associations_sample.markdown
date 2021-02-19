---
layout: post
title:      "Rails Associations Sample"
date:       2021-02-19 14:05:17 -0500
permalink:  rails_associations_sample
---


Associations are one of the most important components when building a Rails project; perhaps the first step one should consider when thinking about a project. Associations seem to be rather difficult or confusing when you think about them.
The confusion seems to lie for the most part within the join table. 

To start understanding associations, let’s go through the following analogy. Imagine a person who likes to collect sneakers. Let’s assume that all the sneakers the person owns come with unique color laces. Also, let’s add to the mix that the collector has three sneakers in his collection. Sneaker 1 has red laces, Sneaker 2 has blue laces and lastly, Sneaker 3 has green laces. Now, let’s think about how we can set up our associations for this example. 

First step-let’s write it down: 

The sneaker owner = The collector => 1st Model => possible attributes could be => name, age and city. 

The Sneaker = Sneaker => 2nd Model => possible attributes could be => brand_name , size. 

Then lace Color = Lace_color => 3rd Model => possible attributes could be => Color. 



The first association that comes to mind is that the collector has three sneakers, has three laces and the sneakers belong to the collector. From here, we can draw the first two models with their associations: 


Model Collector 
```
Class Collector < ApplicationController 
	has_many sneakers 
	has_many laces 			
end 
```

Model Sneaker 

```
Class Sneaker < ApplicationController
	belongs_to collector 
end
```

Next step is to think about the laces. They belong to the sneaker and therefore, they belong to the collector as well. The model will be set up as follows: 

```
Class Lace < ApplicationController
	belongs_to collector 
	belongs_to sneaker	
end
```



Now that we have our models set up, the next natural step is set up the migrations to create the tables. The table below should summarize what the database will look like:


Collectors 	        Sneakers                      	Laces 
  name 	                   brand_name	                 color 
  age 	                      Size                                   collector_id  	                                                    
  city		                                                                 sneaker_id 


The collector_id and the sneaker_id are called foreign keys. They are called as such because they are foreign attributes to the laces’ table. Thanks to those foreign keys, the laces’ table will be the join table. Therefore, we will be able to access the collectors and the sneakers tables. 


Lastly, after setting up the associations, we will be able to use all the accessibility ActiveRecord gives us to query between the tables in order to draw the preferable association. 

