### Tests

A. Test Preparations

For the items listed below, it is recommended to create them before running tests.

* process.env.DB_URI: An URI for a test mongoDB in which new entries, modifications, and queries are stored. You can use a local Mongo database or a remote database from MongoLab.

* process.env.TEST_TOKEN: A token that was issued for a valid Facebook test user. It is used and included in the request headers for restricted route access. Please create a test Facebook user, login to our app from your browser using this test Facebook, grab the token saved under localStorage.token while you are still logged in with the test Facebook in our app. Upon logout, the token will be cleared.

* process.env.TEST_USERID: A valid user ID that is included in some url queries: asking for a user's book inventory and returning a book to an owner. To obtain this value, go to your mongoDB and pick one of the test user IDs from the user's collection.

B. Tests

* Public routes:
Public routes are all GET. Requests are made without any token included.

* Restricted profile routes:
Restricted routes are made with process.env.TEST_TOKEN included in req.token. Tests include: accessing a restricted route without a valid token, getting entries from the database, creating a new entry in the database, patching entries saved in the database, deleting saved entries.

* Restricted admin routes: (Saved for Whitney)
