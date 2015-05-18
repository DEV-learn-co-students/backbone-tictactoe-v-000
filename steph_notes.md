RESOURCES

https://backbonetutorials.com/

CODE SCHOOL

1 Intro video - why we use Backbone / brief intro to view and model

- methods can be disorganized
- might lose the organization in the DOM
- we need an object to maintain the data (models)

MODEL
- how to create a model class and instance
- how to get data from the model. (get and set)
- sync to server (save)
- Use the Backbone.Model.extend to create an Appointment model class
- var Appointment = Backbone.Model.extend({});

VIEW
- responsible for building the HTML
- create view class and instantiate
- rendering the view. every view has a top level ELement.
- instantiate the view and then call render.

- CHALLENGES
- A lot of the calling of methods takes place outside of the instance in their examples, for blake's code, we're calling render from inside the class, so everything happens automatically.

2 MODELS
- Define model class, generate instance, get an attribute (get), set an attribute (set)
- fetching data from the server.
- set urlRoot to make for more restful routes. 
- DEFAULTS 
- EVENTS models can have events
- to listen for event, call .on('event-name', function(){
	alert('event-name happened!');
- todoItem.on([event], [method]);
});
- to run event, call .trigger!
- SPECIAL EVENTS
- change
- destroy
- sync
- error
- all

* A lot of stuff happening in the codeschool tutorial talks about fetching data from the server, but in the case of the tictactoe game, we aren't interacting with a server. (fetch, save stuff, toJSON...none of that is useful to the lab)

3 VIEWS
- can change tag on the el
- can use templating to organize html. can use underscore.js library, which comes with backbone. 
* views are responsible for responding to user interaction
- events: {
	"{event} {selector}": "{method}"
}
- get versus toJSON


4 MODELS & VIEWS
* what about templates?
- update model when something on the view changes
- nice graphics in the slides here
- keep model logic out of the view
- can dynamically set the class on a tag. <h3 class="<%= status %>"></h3>
- need a way to notify view whenever the model changes and re-render. Do this with in initialize in view. this.model.on('change', this.render, this);
- 