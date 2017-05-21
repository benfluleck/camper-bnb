#YelpCamp

This project was completed as part of a Udemy course, it is a fully functional production version of the site. I made a whole host of changes to the original material.

#MyHacks

```
Search on the home page

Made a number of wholesale changes to the UI/UX - using a modified version of 
the Gaia template from creative-Tim

Added ability for users to search

added a number of new routes
added a get comment route

Split out views into separate UI components

Extended the user and campground models

Added a number of new links like My campgrounds, MY Reviews

Added ability for user to edit their own user profile and change passwords

Added ability for user to edit their own campgrounds

Made a number Extended the user, campground models, and added a number of new routes

Added identicon support for users avatar using jdenticon.js

Created an actual logo with a modified version of a logo from the Noun Project


```

I will be launching a Udemy course on how I extended the original YelpCamp into a fully fledged app.

## Additional Code Examples

```
//SEARCH POST ROUTE
router.post("/search", function (req,res){ 
      var search = req.body.search;
	  if (search){
		res.redirect("/search?q="+search)
	  }
	  else {
	     res.redirect("/search")
	  }
})

//SEARCH GET ROUTE
router.get("/search", function (req,res){
	var query = req.query["q"]
	if (query){//if search then search
        Campground.find({location: new RegExp(query, 'i')}, function(err, campgrounds){
            if (err){
                console.log(err)
            }
            else{
                res.render("campgrounds/search", {campgrounds, query})
            }
        })
    }
    else {
        Campground.find({}, function(err, campgrounds){
            if (err){
                console.log(err)
            }
            else{
                res.render("campgrounds/search", {campgrounds, query: "/search"})
            }
        })
    }
})
```

Show what the library does as concisely as possible, developers should be able to figure out **how** your project solves their problem by looking at the code example. Make sure the API you are showing off is obvious, and that your code is short and concise.

## Motivation

This project was a built as a side project over a few weeks, to pull all the knowledge I have gained over the years in front end dev into one project.

## Useful Links

* [OluOmoniyi](http://www.oluomoniyi.com) - personal website
* [theazimuth.co](http://www.theazimuth.co) - Company Website

* [udemy](https://www.udemy.com/the-web-developer-bootcamp/) - Udemy course, cant recommend it enough to be honest!
* [unsplash](http://www.unsplash.com) - Amazing image source
* [jdenticon](http://www.jdenticon.com) - Generates user avatar from random seed data
* [nounproject](http://www.nounproject.com) - Starter user logo
* [nounproject](http://www.fontawesosome.com) - font icons

## License

Do as you please with it, if you find it useful drop me a message (MIT, Apache, etc.)
