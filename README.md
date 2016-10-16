# Running server for data
This works with fuse FetchTest demo. Note: its on Mongodb 1.3 from 2014. https://github.com/aarmand/mongodb-express-2014
## Using it
1. In terminal run $mongod
2. then run ```$ node mongodb-express-2014/index.js```

# Fetching and Displaying Data Example
Example project to accompany the "Fetching and Displaying Data" Fuse tutorial video. This is a super basic example, and uses the [JSONPlaceholder fake online REST API](http://jsonplaceholder.typicode.com) to grab a bunch of picture data and display them using a FuseJS Observable and data binding. All relevant code is in the `MainView.ux` file.

## Fuse version
This example was produced with Fuse (beta) v0.8.3. It was later updated to be compatible with Fuse 0.20 and onwards.

## Branches
The "finished product" is on the `master` branch, and the template I started with in the video is on the `starting-template` branch.

## License
This code is licensed under the BSD2 license (see LICENSE).

## Places Implentation Notes
My places server is not throwing error codes for non existent paths. Remember that it dynamically generates paths based on the inputs. So in theory seems it will always find a path and just return the results there. If there is nothing there, it will return an empty object or array. I need to fix this. But in the meantime, the status error in the fusetools fetch example re: status !== wont through because we dont have one set on the error.

Looks like server is sending 400 status but Fuse not receiving. Why? Debug send to make sure its sending.

Figured out that response is being sent but something is going on with the response code. When we get rid of the response code check, results get rendered.

Built a server for db routing. Start server before running fuse
