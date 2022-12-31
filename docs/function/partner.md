## Partners

The following are the helper functions under the partners directory


# **business_units_for_select function**:

Description: This function returns the business units of the current organisation if the current staff member is an admin, or the business units assigned to the current staff member if they are not an admin.

Input parameters:

None.
Output values:

The business units of the current organisation if the current staff member is an admin, or the business units assigned to the current staff member if they are not an admin.
Error conditions:

If the current_organisation or current_staff_member objects are nil, the function returns nil.
Examples of usage:


    business_units_for_select # returns the business units of the current organisation if the current staff member is an admin, or the business units assigned to the current staff member if they are not an admin

# **preference_groups_json function**:

Description: This function generates a JSON array of preference groups, including their IDs, titles, and the titles of their questions.

Input parameters:

preference_groups (collection): A collection of preference group objects.
Output values:

A JSON array of preference groups, including their IDs, titles, and the titles of their questions.
Error conditions:

If the preference_groups parameter is `nil