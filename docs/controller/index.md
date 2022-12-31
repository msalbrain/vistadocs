
## Folder structure

```

    ├───controllers
        ├───admin
        │   ├───articles
        |   |
        │   ├───categories
        │   ├───partner_categories
        │   ├───staff
        │   └───vista_admins
        ├───api
        │   ├───admin
        │   │   ├───branches
        │   │   └───staff_members
        │   ├───partners
        │   │   └───v1
        │   │       ├───management
        │   │       └───staff
        │   └───v1
        │       ├───branches
        │       ├───categories
        │       ├───questions
        │       ├───sync
        │       └───users
        ├───concerns
        └───partners
            ├───staff
            └───staff_members    
```



## **ApplicationController**

The ApplicationController is a base class for all the controllers in a Ruby on Rails application. It provides a number of common features that are useful in most controllers, such as support for flash messages and handling of exceptions.

Here is a description of each part of the ApplicationController:

 + include Pundit: This line includes the Pundit module, which provides a set of helper methods for authorization in the controller.

 + protect_from_forgery with: :exception: This line enables protection against cross-site request forgery (CSRF) attacks. If a request is determined to be a forgery, an exception will be raised.

 + add_flash_types :success, :error, :warning: This line adds custom flash types (e.g., :success, :error, :warning) that can be used to display flash messages to the user.

 + layout :layout_by_resource: This line specifies a method (layout_by_resource) that will be used to determine the layout to use for the current request.

 + devise_group :non_user, contains: %i[vista_admin staff_member]: This line specifies a group of Devise models (e.g., :vista_admin, :staff_member) that are treated as "non-users" for the purposes of Devise authentication.

 + def info_for_paper_trail: This method returns a hash containing information about the current request (e.g., the IP address and user agent) that can be used by the PaperTrail gem to track changes in the application.

 + def layout_by_resource: This method returns the name of the layout to use for the current request. If the current controller is a Devise controller, it returns 'devise', otherwise it returns 'application'.

 + def convert_params_to_snakecase: This method converts the keys of the params hash to snakecase (e.g., 'userName' becomes 'user_name').

As the ApplicationController is a base class, it does not handle any routes or interact with any models directly. Instead, it provides common functionality that can be used by other controllers in the application.

Error conditions that may be handled by the ApplicationController include CSRF attacks and other exceptions that may be raised during the handling of a request.

Examples of usage for the ApplicationController might include setting flash messages or handling exceptions in controllers that inherit from it. For example:


    class PostsController < ApplicationController
    def create
        @post = Post.new(post_params)
        if @post.save
        flash[:success] = 'Post created successfully'
        redirect_to posts_path
        else
        flash[:error] = 'There was an error creating the post'
        render :new
        end
    end
    end

In this example, the PostsController inherits from ApplicationController and makes use of the custom flash types (:success and :error) defined in the base class. It also utilizes the protect_from_forgery feature to protect against CSRF attacks.




