## Models

### Folder structure
```
    ├───models
        ├───concerns
        ├───personality
        └───versions
```


# **Address**
The Address model represents an address in the system. It has the following attributes:

**id** (integer): a unique ID for the address

**label** (string): a label or nickname for the address

**line1** (string): the first line of the address

**line2** (string): the second line of the address

**town** (string): the town or city where the address is located

**county** (string): the county or region where the address is located

**postcode** (string): the postal code for the address

**country** (string): the country where the address is located

**phone** (string): a phone number associated with the address

**latitude** (decimal): the latitude of the address

**longitude** (decimal): the longitude of the address

**addressable_type** (string): the type of model that the address belongs to** (e.g. "User" or "Company")

**addressable_id** (integer): the ID of the model that the address belongs to

**created_at** (datetime): the date and time that the address was created

**updated_at** (datetime): the date and time that the address was last updated

**city_id** (integer): the ID of the city where the address is located

The Address model has the following relationships:

    belongs_to :addressable, polymorphic: true: this indicates that the address belongs to a parent model, and the addressable_type and addressable_id attributes are used to specify which model the address belongs to. The polymorphic option indicates that the parent model can be any type of model, and the inverse_of: :address option specifies the name of the has_one or has_many association on the parent model.
    belongs_to :city: this indicates that the address belongs to a city. The city_id attribute is used to specify which city the address belongs to.

The Address model has the following custom methods:

    country_name: this method returns the name of the country for the address. It uses the ISO3166 gem to look up the name of the country based on the country attribute.
    country_code: this method returns the country code for the address. It simply returns the value of the country attribute.

Here are some examples of how the Address model might be used:
    # Find all addresses for a user
    user = User.find(123)
    addresses = user.addresses

    # Find the nearest address to a given location
    latitude = 37.774929
    longitude = -122.419416
    radius = 5 # miles
    addresses = Address.within(radius, origin: [latitude, longitude])

    # Find the address for a specific user
    user = User.find(123)
    address = user.address

    # Set the address for a user
    user = User.find(123)


# **Admin**

The following are the Attributes of Admin:

**id**: bigint, primary key for the model

**email**: string, the email address of the admin

**first_name**: string, the first name of the admin

**last_name**: string, the last name of the admin

**mobile_number**: string, the mobile phone number of the admin

**encrypted_password**: string, a hashed version of the admin's password

**reset_password_token**: string, a token used for resetting the admin's password

**reset_password_sent_at**: datetime, the time at which the reset password token was sent

**remember_created_at**: datetime, the time at which the admin selected the "remember me" option during login

**sign_in_count**: integer, the number of times the admin has signed in

**current_sign_in_at**: datetime, the time at which the admin signed in during the current session

**last_sign_in_at**: datetime, the time at which the admin signed in during the previous session

**current_sign_in_ip**: inet, the IP address of the admin during the current session

**last_sign_in_ip**: inet, the IP address of the admin during the previous session

**authentication_token**: string, a token used for authenticating the admin

**created_at**: datetime, the time at which the admin's record was created

**updated_at**: datetime, the time at which the admin's record was last updated

**organisation_id**: bigint, the ID of the organization to which the admin belongs

**type**: string, the type of staff member (in this case, "Admin")

**employee_id**: string, the employee ID of the admin

**confirmation_token**: string, a token used for confirming the admin's email address

**confirmed_at**: datetime, the time at which the admin's email address was confirmed

**confirmation_sent_at**: datetime, the time at which the confirmation token was sent

**suspended_at**: datetime, the time at which the admin's access was suspended

**archived_at**: datetime, the time at which the admin's record was archived

**encrypted_pin**: string, a hashed version of the admin's PIN (personal identification number)

**unconfirmed_email**: string, the unconfirmed email address of the admin (if the admin has requested a change to their email address)

Inherits from [StaffMember](./#staffmember) model

Custom methods: None

Examples of usage:

    An instance of the Admin model could represent a staff member with administrative privileges within an organization.
    The email, password, and authentication token attributes could be used for authenticating the admin when logging in to the system.
    The sign_in_count, current_sign_in_at, and last_sign_in_at attributes could be used for tracking the admin's login history.


# **Answer**
Attributes:

**id**(integer): The primary key for the model.

**question_id**(integer): The ID of the question that the answer belongs to.

**title**(text): The title of the answer.

**description**(text): A description of the answer.

**created_at**(datetime): The timestamp for when the answer was created.

**updated_at**(datetime): The timestamp for when the answer was last updated.

**position**(integer): The position of the answer within its parent question.

Relationships:

**question**(belongs_to): The question that the answer belongs to.

**photo**(has_one): The photo associated with the answer.
    
Custom methods:

**siblings**: Returns the other answers within the same question as the current answer.

**reject_photo?**: Determines whether a photo should be rejected when creating or updating an answer.

**set_position**: Sets the position of the answer within its parent question.

Examples of usage:

    # Create a new answer with a title and description
    answer = Answer.new(title: 'Yes', description: 'The answer is yes')

    # Set the question that the answer belongs to
    answer.question = Question.first

    # Save the answer
    answer.save

    # Update the title of the answer
    answer.title = 'Yes, definitely'
    answer.save

    # Delete the answer
    answer.destroy

# **ApplicationRecord**
Attributes:

None. ApplicationRecord is an abstract base class and does not have any attributes of its own.

Relationships:

None. ApplicationRecord is an abstract base class and does not have any relationships of its own.
Custom methods:

updated_since(datetime): Returns all records that have been updated since the specified datetime.
pluck_to_hash(*keys): Returns an array of hashes, where each hash represents a record in the database with keys corresponding to the specified attributes.

Examples of usage:

    # Find all records in the database that have been updated since yesterday
    ApplicationRecord.updated_since(1.day.ago)

    # Retrieve the IDs and titles of all records in the database
    ApplicationRecord.pluck_to_hash(:id, :title)
    Note: ApplicationRecord is an abstract base class and cannot be instantiated directly. Instead, you will need to use a concrete subclass of ApplicationRecord (such as Answer, Question, etc.) to create and manipulate records in the database.



# **ArticleContentCategory**

Attributes:


**id**(integer): The primary key for the model.

**article_id**(integer): The ID of the article that the content category belongs to.

**content_category_id**(integer): The ID of the content category.

**created_at**(datetime): The timestamp for when the article content category was created.

**updated_at**(datetime): The timestamp for when the article content category was last updated.

Relationships:


**article**(belongs_to): The article that the content category belongs to.

**content_category**(belongs_to): The content category.
Custom methods:

None.
Examples of usage:


    # Create a new article content category
    article_content_category = ArticleContentCategory.new

    # Set the article and content category that the article content category belongs to
    article_content_category.article = Article.first
    article_content_category.content_category = ContentCategory.first

    # Save the article content category
    article_content_category.save

    # Delete the article content category
    article_content_category.destroy



# **Article**

Attributes:

**id**(integer): The primary key for the model.

**title**(string): The title of the article.

**content**(text): The content of the article.

**publish_at**(datetime): The timestamp for when the article should be published.

**created_at**(datetime): The timestamp for when the article was created.

**updated_at**(datetime): The timestamp for when the article was last updated.

**notification_job_id**(integer): The ID of the job used to send notifications when the article is published.

Relationships:

**header_image**(has_one): The header image for the article.

**photos**(has_many): The photos associated with the article.

**article_content_categories**(has_many): The article content categories associated with the article.

**content_categories**(has_many): The content categories associated with the article.

Custom methods:

**header_image=(header_image)**: Sets the header image for the article.

**publish_at=(publish_at)**: Sets the publish timestamp for the article.

**published?**: Returns true if the article has been published, false otherwise.

**status**: Returns the current status of the article.

**self.start_draft**: Creates a new draft article.

Examples of usage:


    # Create a new article
    article = Article.new

    # Set the title and content of the article
    article.title = 'My article'
    article.content = 'This is the content of my article'

    # Set the publish timestamp for the article
    article.publish_at = 1.day.from_now

    # Save the article
    article.save

    # Check if the article has been published
    article.published?

    # Get the status of the article
    article.status

    # Delete the article
    article.destroy


# **AuthenticationToken**

The AuthenticationToken model represents a token that is used to authenticate a user. It belongs to a polymorphic user, which means that it can belong to any model that includes the User module.

Attributes:


**id**: a unique identifier for the token (integer, primary key)

**context**: the context in which the token is used (string)

**body**: the actual token (string)

**user_type**: the type of the user that the token belongs to (string)

**user_id**: the ID of the user that the token belongs to (integer)

**last_used_at**: the last time the token was used (datetime)

**ip_address**: the IP address from which the token was last used (inet)

**user_agent**: the user agent string from the device that used the token last (string)

**created_at**: the time the token was created (datetime)

**updated_at**: the time the token was last updated (datetime)

Relationships:


**user**: the user that the token belongs to (polymorphic association)

Custom methods:


**decode**: decodes a token from the headers

**find_for_context**: finds a token for a given context and token body

**create_and_return_staff_token**: creates a new staff token and returns it

**create_and_return_manager_token**: creates a new manager token and returns it

**create_and_return_token**: creates a new token for a given context and returns it

**create_and_return_analytics_token**: creates and returns an analytics token

Examples of usage:

    To create a new staff token for a user:

    
    token = AuthenticationToken.create_and_return_staff_token(current_user, request)
    To find a token for a given context and token body:

    
    token = AuthenticationToken.find_for

# **BranchCategorisation**
The BranchCategorisation model represents the many-to-many relationship between branches and partner categories. This allows a branch to be associated with one or more partner categories, and a partner category to be associated with one or more branches.

Attributes:


**id**: A unique identifier for the branch categorisation record, stored as an integer and generated automatically by the database.

**branch_id**: The ID of the branch that is associated with a partner category, stored as an integer.

**partner_category_id**: The ID of the partner category that is associated with a branch, stored as an integer.

**created_at**: A timestamp indicating when the branch categorisation record was created, stored as a datetime.

**updated_at**: A timestamp indicating when the branch categorisation record was last updated, stored as a datetime.

Relationships:


**belongs_to**: A branch categorisation belongs to a single branch and a single partner category.


**branch**: This relationship specifies the branch that is associated with a partner category.


**partner_category**: This relationship specifies the partner category that is associated with a branch.

Custom methods:

There are no custom methods defined for the BranchCategorisation model.

Examples of usage:

Creating a new branch categorisation:

    branch = Branch.first
    partner_category = PartnerCategory.first
    branch_categorisation = BranchCategorisation.new(branch: branch, partner_category: partner_category)
    branch_categorisation.save

Retrieving all branch categorisations for a particular branch:

    branch = Branch.first
    branch_categorisations = branch.branch_categorisations

Retrieving all branches that belong to a particular partner category:

    partner_category = PartnerCategory.first
    branches = partner_category.branches

Removing a branch categorisation:

    branch_categorisation = BranchCategorisation.first
    branch_categorisation.destroy


# **BranchManager**
The BranchManager model is a subclass of the StaffMember model and represents a staff member who is a branch manager at an organisation.

attributes:

**id**: a bigint that serves as the primary key for the model

**email**: a string that stores the email address of the staff member

**first_name**: a string that stores the first name of the staff member

**last_name**: a string that stores the last name of the staff member

**mobile_number**: a string that stores the mobile phone number of the staff member

**encrypted_password**: a string that stores the encrypted password of the staff member

**reset_password_token**: a string that stores a token used to reset the staff member's password

**reset_password_sent_at**: a datetime that stores the time at which the reset password token was sent to the staff member

**remember_created_at**: a datetime that stores the time at which the staff member requested to be remembered on the device they are using

**sign_in_count**: an integer that stores the number of times the staff member has signed in

**current_sign_in_at**: a datetime that stores the time at which the staff member last signed in

**last_sign_in_at**: a datetime that stores the time at which the staff member signed in before the last time they signed in

**current_sign_in_ip**: an inet data type that stores the IP address the staff member is currently signed in from

**last_sign_in_ip**: an inet data type that stores the IP address the staff member last signed in from

**authentication_token**: a string that stores a unique token used for authentication purposes

**created_at**: a datetime that stores the time at which the staff

Relationships:

BranchManager has a one-to-many relationship with Branch through the branches association.

Custom methods:

assigned_branches: returns a collection of branches that the branch manager is assigned to.

Examples of usage:


    # Find a branch manager by their email and assign them to a branch
    manager = BranchManager.find_by(email: 'branch_manager@example.com')
    branch = Branch.find(1)
    manager.branches << branch

    # Find all the branches that a branch manager is assigned to
    manager = BranchManager.find(1)
    manager.assigned_branches


# **Branch**
Attributes:

**id: integer, primary key

**business_unit_id: integer

**name: string

**created_at: datetime

**updated_at: datetime

**email: string

**telephone: string

**archived_at: datetime

**image: string

**branch_info: string

**booking_url: string

**vista_partner: boolean, default: false

**ratings_count: integer, default: 0


Relationships:

business_unit: belongs to a BusinessUnit
organisation: has one Organisation through the BusinessUnit
photo: has one Photo as owner
address: has one Address as addressable
staff_assignments: has many StaffAssignments as target
staff_members: has many StaffMembers through StaffAssignments
shares: has many Shares
users: has many Users through Shares with the condition that the Share is authorised
branch_categorisations: has many BranchCategorisations
categories: has many PartnerCategories through BranchCategorisations
interactions: has many Interactions
roles: has many Roles through the BusinessUnit
check_ins: has many CheckIns
member_requests: has many MemberRequests
member_request_messages: has many MemberRequestMessages as messageable

Custom methods:

category_titles: returns an array of the titles of the categories associated with the branch
destroy_staff: destroys the staff members associated with the branch


# **BusinessUnit**

Attributes:

**id**: integer, primary key

**name**: string

**organisation_id**: integer, foreign key to the organisations table

**created_at**: datetime

**updated_at**: datetime

**archived_at**: datetime

Relationships:


**belongs_to**:organisation

**has_many**:branches

**has_many**:roles

**has_many**:member_request_types

Custom methods:

None

Examples of usage:

Fetch all business units belonging to a particular organisation:

    organisation = Organisation.find(1)
    business_units = organisation.business_units
Fetch all branches belonging to a particular business unit:

    business_unit = BusinessUnit.find(1)
    branches = business_unit.branches
Fetch all roles belonging to a particular business unit:

    business_unit = BusinessUnit.find(1)
    roles = business_unit.roles
Fetch all member request types belonging to a particular business unit:

    business_unit = BusinessUnit.find(1)
    member_request_types = business_unit.member_request_types

# **CategoryUpdate**
Attributes:


**id**: integer

**category_id**: integer

**question_ids**: array of integers

**created_at**: datetime

**updated_at**: datetime

Relationships:


**belongs_to**:category

**Custom methods**:


**title**: returns the title of the associated category

**photo**: returns the photo of the associated category

**questions**: returns an array of Question objects that have an id in the question_ids attribute

Examples of usage:



Find the category update with id 1
   
    update = CategoryUpdate.find(1)

Access the title of the associated category
   
    update.title
   
Access the photo of the associated category
   
    update.photo

Access the questions associated with this update
   
    update.questions


# **Category**

# **CheckIn**

# **City**

# **ContentCategory**

# **DataImport**

# **Device**

# **Feed**

# **Ignore**

# **Interaction**

# **MemberRequestMessage**

# **MemberRequestTypeAssignment**

# **MemberRequestType**

# **MemberRequest**

# **Notification**

# **Organisation**

# **PartnerCategory**

# **Personality**

# **Photo**

# **PreferenceGroup**

# **ProfileRequest**

# **Question** 

# **Rating**

# **Release**

# **RoleAssignment**

# **RolePreferenceGroupAssignment**

# **Role**

# **Share**

# **StaffAssignment**

# **StaffMember**

# **TopQuestion**

# **UserAnswer**

# **User**

# **VideoContentCategory**

# **Video**

# **VistaAdmin**


