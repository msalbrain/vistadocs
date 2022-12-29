## Models

# Address
The Address model represents an address in the system. It has the following attributes:

    id (integer): a unique ID for the address
    label (string): a label or nickname for the address
    line1 (string): the first line of the address
    line2 (string): the second line of the address
    town (string): the town or city where the address is located
    county (string): the county or region where the address is located
    postcode (string): the postal code for the address
    country (string): the country where the address is located
    phone (string): a phone number associated with the address
    latitude (decimal): the latitude of the address
    longitude (decimal): the longitude of the address
    addressable_type (string): the type of model that the address belongs to (e.g. "User" or "Company")
    addressable_id (integer): the ID of the model that the address belongs to
    created_at (datetime): the date and time that the address was created
    updated_at (datetime): the date and time that the address was last updated
    city_id (integer): the ID of the city where the address is located

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


# Admin

Attributes:

id: bigint
email: string
first_name: string
last_name: string
mobile_number: string
encrypted_password: string
reset_password_token: string
reset_password_sent_at: datetime
remember_created_at: datetime
sign_in_count: integer
current_sign_in_at: datetime
last_sign_in_at: datetime
current_sign_in_ip: inet
last_sign_in_ip: inet
authentication_token: string
created_at: datetime
updated_at: datetime
organisation_id: bigint
type: string
employee_id: string
confirmation_token: string
confirmed_at: datetime
confirmation_sent_at: datetime
suspended_at: datetime
archived_at: datetime
encrypted_pin: string
unconfirmed_email: string
Relationships:

Inherits from StaffMember model
Custom methods: None

Examples of usage:

An instance of the Admin model could represent a staff member with administrative privileges within an organization.
The email, password, and authentication token attributes could be used for authenticating the admin when logging in to the system.
The sign_in_count, current_sign_in_at, and last_sign_in_at attributes could be used for tracking the admin's login history.
The organisation_id attribute could be used to associate the admin with a specific organization.
The suspended_at attribute could be used to temporarily suspend the admin's access to the system.

# Answer

# ApplicationRecord

# ArticleContentCategory

# Article

# AuthenticationToken

# BranchCategorisation

# BranchManager

# Branch

# BusinessUnit

# CategoryUpdate

# Category

# CheckIn

# City

# ContentCategory

# DataImport

# Device

# Feed

# Ignore

# Interaction

# MemberRequestMessage

# MemberRequestTypeAssignment

# MemberRequestType

# MemberRequest

# Notification

# Organisation

# PartnerCategory

# Personality

# Photo

# PreferenceGroup

# ProfileRequest

# Question 

# Rating

# Release

# RoleAssignment

# RolePreferenceGroupAssignment

# Role

# Share

# StaffAssignment

#  StaffMember

# TopQuestion

# UserAnswer

# User

# VideoContentCategory

# Video

# VistaAdmin


