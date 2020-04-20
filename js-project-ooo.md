# JS/Rails Order of Operations Guide

The JavaScript Project repo has a handful of helpful [READMEs](https://github.com/learn-co-students/js-spa-project-instructions-online-web-sp-000) that outline the requirements for the JS/Rails Project along with project planning tips and a note about what to expect during your review. There is also this [JavaScript Rails API Project Setup README](https://github.com/learn-co-curriculum/mod3-project-week-setup-example) that provides a thorough step by step walkthrough to get your project up and running along with some help OOJS refactoring tips. Lastly, we also wanted to outline a suggested flow of execution to aide you in building your project. We put together this "Order of Operations Guide" for organizing and completing your JS/Rails Project. This guide is based on the 4-part project build. All study groups can be found [here](https://learn.co/study-groups).

The application we will create during the project build series is a "Syllabus Sharing App" for independent study.

 **USER STORY: A user should be able to read and create syllabi based on category**

## Checklist

### PART 1: Planning and Building a Rails API

**BEFORE YOU CODE**
- [ ] 1. Check project requirements in [JavaScript READMEs](https://github.com/learn-co-students/js-spa-project-instructions-online-web-sp-000)
- [ ] 2. Ideate! What do you want to build?
    - choose a domain you're familiar with!
    - choose a domain you care about
- [ ] 3. Wireframing & User Stories
    - Write down your models, their attributes, and their associations
    - "As a user, I can ....."
    - "A user should be able to ....."
    - What does your app _do_?
- [ ] 4. Design your MVP = 'Minimum Viable Product' vs. what are my 'stretch goals'
    - Stretch goals - bonus features you want but don't need

**NOW WE'RE READY FOR PROJECT SET UP**

- [ ] 5. Generate new [Rails API](https://edgeguides.rubyonrails.org/api_app.html) using `rails new <my_app_name> --database=postgresql --api`
    - (Replace `<my_app_name>` with the actual name of your project)
- [ ] 6. Create github repo
- [ ] 7. Create a new branch for building out models. This way you can always go back to the fresh API.
    - **NOTE**: It is best practice to always create a new branch when working on a new feature/edit to your code. Your master branch should only have working code. Debug in a branch, not in master.

**NOW WE'RE READY TO CODE (BUT JUST OUR MODELS — NO CONTROLLERS OR SERIALIZERS YET)**

**NOTE**: Remember to _**VERTICALLY**_ build your MVP! This means building out one model/feature at a time. DO NOT build out _all_ the models and controllers at the same time. This is the easiest way to get lost in your project very early. Read more about this [here](https://github.com/learn-co-students/js-spa-project-instructions-online-web-sp-000/blob/master/project-planning-tips.md#build-vertically-not-horizontallys).

- [ ] 8. Build your models
    - Migrations
    - Model classes
    - Associations
- [ ] 9. Test your models and associations in the console
    - Create some seed data
    - Adjust migrations as needed


### PART 2: Routes, Controllers, Serializers

- [ ] 1. Name spaced routes
- [ ] 2. Controllers rendering JSON based on routes
- [ ] 3. Fast JSON Serializer

<!--

**NOW, CONSIDER USER CONTROLLER, APPLICATION CONTROLLER, AND VIEWS**

*IMPORTANT:* Build views and controller actions based on the flow of your app, one step at a time, testing as you go!

- Use `shotgun` and `pry` (or `raise`/`inspect`) all the time!

**START WITH LOGIN**

- [x] 9. Create your `UsersController`
  - Mount new controller in `config.ru` with `use UsersController` (Why do we add this?)

- [x] 10. Enable `sessions` in `ApplicationController`
    - Enable sessions
    - Create session secret

- [x] 11. Build routes and views for login
  - Build your `get` login route + "login" view
  - Build your `post` login route
      - **Tip**: Here is where we authenticate the user and leverage the session hash to log them in!
  - Build your `get users/:id` route + "show" view

- [x] 12. Create your `ApplicationController` helper methods
  - **Ask**: Why do we add this?
  - `#logged_in?`: checks if the user is logged in
  - `#current_user`: keeps track of the user currently logged in

**MOVE ON TO SIGN UP**
- [x] 13. Build routes and views for signup
  - Build your `get` signup route + "signup" view
  - Build your `post` signup route

**WRAP UP WITH LOG OUT**
- [x] 14. Build your `get` logout route

### PART 3 — CRUD: Create, Read, Update, Delete

- [x] 15. Create your `PostsController`
  - Mount new controller in `config.ru` with `use PostsController`
  - **Ask**: Why do we add this? ^

- [x] 16. Implement READ functionality
  - Create `get` posts route
  - Create a view for displaying all posts
  - Create show route

- [x] 17. Implement CREATE functionality
  - Create `get` posts route and view to render form
  - Create `post` route to create new post

- [x] 18. Implement UPDATE functionality
  - Add `use Rack::MethodOverride` in `config.ru`
  - **Ask**: Why do we add this? ^
  - Create `get` route and view to render form
  - Create `patch` route to update an existing post

- [x] 19. Implement DELETE functionality
  - Create `delete` form in relevant view
  - Create `delete` route to delete post

### PART 4 — Tighten Up!: Validations and Authorization
- [x] 20. Implement `sinatra-flash` gem to display validation failures and improve user experience (UX)
  - Review the [docs](https://github.com/SFEley/sinatra-flash)
  - **Tip**: a `flash[:message]` has the lifecyle of one `GET` request and will not show up when rendering an `erb` file.
- [x] 21. Include ActiveRecord validations in your `User` and `Post` model that checks for user inputs
  - **Ex**: Making sure all form fields are filled out or that a user is using a unique email or username
  - Review the [docs](https://guides.rubyonrails.org/active_record_validations.html)
  - **Tip**: `has_secure_password` has a built in validation for the `password_digest` attribute!
- [ ] 22. Leverage the `logged_in?` helper method in the controller and/or views to implement authorization for creating a new post.
  - Make sure a user can't create a new post without being logged in.
- [ ] 23. Implement authorization to edit and delete.
  - Make sure a user can't edit or delete a post that doesn't belong to them.
- [ ] 24. Refactor your code to make it more DRY!
  - **Ask**: Where am I repeating myself?
- [ ] 25. Create a `README.md`
  - Include a short description, install instructions, a contributors guide and a link to the license for your code -->

### Bonus
- [ ] Leverage a CSS framework to improve the styling of your application
  - Easiest to implement: [Bulma](https://bulma.io/)
  - Most popular: [Bootstrap](https://getbootstrap.com/)
  - Also good: [Semantic UI](https://semantic-ui.com/)
  - Not bootstrap: [Materialize](https://materializecss.com/)

### Confirm
- [ ] You have a large number of small Git commits
- [ ] Your commit messages are meaningful
- [ ] You made the changes in a commit that relate to the commit message
- [ ] You don't include changes in a commit that aren't related to the commit message
