What makes angular so different?
    + Its directives enable a lot of functionality
    + data binding
    + reusable components
    + attach new behavior to DOM elements
Conventions
    + core identifiers always start with a '$'
Templates
    + objects defined here can become model properties
        + can be used in the invoked controller function
Directives
    + apply special behavior
    + DOM manipulation
    + has different types such as ng-app, ng-repeat, and ng-model
        + ng-model: stores/updates the value of the input field into/from a variable
        + ng-app: initializes the application
        + ng-controller: instantiates new Controller object using its constructor
Expressions
    + {{ expression | filter }}
        + will replace evaluated value of expression with the filter in the view
        + ex. {{qty * cost | currency}}
Scope
    + scope is where the variables are stored
    + scope is the "model"
    + execution context for expressions
    + ties the scope into the controller
    + during the template linking phaes, the directives set up a $watch expression on the scope
    + controllers and directives both  reference the scope but no teach other
    + good for eliminating interdependency
    + there is one root scope, but many child/descendent scope
        + scopes created by directives are all rooted off of its parent scope
        + similar to the DOM tree
    + scopes can also propagate events, similar to DOM events
    + Lifecycle
        1. Creation
        2. Watcher registration
        3. Model mutation
        4. Mutation observation
        5. Scope destruction
Controllers
    + specifies a constructor function to create an object
    + aka controllers specify variables and functionality for expressions and directives
    + you can instanitate controllers in the HTML template, and access its functions
    + if functionality is not specific, then move it out into a service
    + controllers can also use functions defined in services
        + this is done through dependency injection (DI)
    + after being instantiated in the template, a new child scope is created
        + child scope can then be injected as $scope in the constructor
        + basically sets up initial state of $scope
        + adds behavior to the $scope object
    + define the intial state of scope in the controller
    + access the state by data binding {{ greeting }}
    + Assigning a property to $scope creates or updates the model
Services
    + built-in services are denoted with "$"
    + available for use for all parts of the application
    + various ways to specify creation, ie. anonymous factory function
        + this registers a factory function that will create a service id instance when called
    + AngularJS services are lazily instantiated
        + only instantiated when an application component depends on it
    + They are lazily instantiated
Data Binding
    + sync data between the model and the view
    + binding is done in the template
    + Beauty of Angular data binding: two way merge between the view and the model
    + controller is independent of the view
