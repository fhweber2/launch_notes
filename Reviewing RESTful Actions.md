###Reviewing RESTful Actions

It is important to review how our resources map to RESTful actions, and how those actions correlate to our database CRUD operations.

####For the issues resource:
		
    A POST to /issues creates an issue
    A GET to /issues retrieves the collection of issues
    A GET to /issues/3 retrieves the issue with an id of 3
    A PUT to /issues/3 updates the issue with an id of 3
    A DELETE to /issues/3 destroys the issue with an id of 3
