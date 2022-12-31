## Admin

The following are the helper functions under the admin directory

# **category_parent_selection function**

Description: This function generates an array of arrays containing category names and IDs, with each category's ancestors included in the name. The resulting array is sorted by the category name.

Input parameters:

None.
Output values:

An array of arrays containing category names and IDs, with each category's ancestors included in the name, sorted by the category name.
Error conditions:

None.
Examples of usage:


    category_parent_selection # returns an array of arrays containing category names and IDs, with each category's ancestors included in the name, sorted by the category name





# **render_partner_categories function**

Description: This function renders a sortable list of categories using the render_sortable function and the provided reorder_admin_partner_categories_path URL.

Input parameters:

categories (collection): A collection of categories to be rendered.
Output values:

A rendered list of categories.
Error conditions:

If the categories parameter is nil or empty, the function returns nil.
Examples of usage:

    render_partner_categories(Category.all) # renders a sortable list of all categories using the provided `reorder_admin_partner_categories_path` URL

# **render_categories function**

Description: This function renders a sortable list of categories using the render_sortable function and the provided reorder_admin_categories_path URL.

Input parameters:

categories (collection): A collection of categories to be rendered.
Output values:

A rendered list of categories.
Error conditions:

If the categories parameter is nil or empty, the function returns nil.
Examples of usage:


    render_categories(Category.all) # renders a sortable list of all categories using the provided `reorder_admin_categories_path` URL

# **render_sortable function**

Description: This function renders a sortable list of items using the provided URL.

Input parameters:

collection (collection): A collection of items to be rendered.
url (string): The URL to be used for sorting the items.
Output values:

A rendered list of items.
Error conditions:

If the collection parameter is nil or empty, the function returns nil.
Examples of usage:


    render_sortable(Category.all, reorder_admin_categories_path) # renders a sortable list of all categories using the provided URL



# **import_status function**

Description: This function returns an icon and text representing the status of a data import.

Input parameters:

data_import (object): An object representing a data import. The object should have a status attribute.
Output values:

An icon and text representing the status of the data import.
Error conditions:

If the data_import parameter is nil, the function returns nil.
If the status attribute of the data_import object is not one of the expected values ("new", "running", "finished", "failed"), the function returns nil.
Examples of usage:


    import_status(DataImport.first) # returns an icon and text representing the status of the first data import in the database


# **navbar_breadcrumbs function**

Description: This function generates a breadcrumb navigation element with the specified options.

Input parameters:

None.
Output values:

A breadcrumb navigation element with the specified options.
Error conditions:

None.
Examples of usage:


    navbar_breadcrumbs # generates a breadcrumb navigation element with the specified options


# **category_selection function**

Description: This function generates an array of arrays containing category names and IDs, with each category's ancestors included in the name, for all non-root categories. The resulting array is sorted by the category name.

Input parameters:

None.
Output values:

An array of arrays containing category names and IDs, with each category's ancestors included in the name, for all non-root categories, sorted by the category name.
Error conditions:

None.
Examples of usage:


    category_selection # returns an array of arrays containing category names and IDs, with each category's ancestors included in the name, for all non-root categories, sorted by the category name



# **release_status function**

Description: This function returns an icon and text representing the status of a release.

Input parameters:

release (object): An object representing a release. The object should have a status attribute.
Output values:

An icon and text representing the status of the release.
Error conditions:

If the release parameter is nil, the functi codeon returns nil.
If the status attribute of the release object is not one of the expected values ("queued", "processing", "complete"), the function returns nil.
Examples of usage:


    release_status(Release.first) # returns an icon and text representing the status of the first release in the database


# **published_status function**

Description: This function returns a string indicating whether a video is published or not.

Input parameters:

video (object): An object representing a video. The object should have a published? method.
Output values:

A string indicating whether the video is published or not.
Error conditions:

If the video parameter is nil, the function returns nil.
Examples of usage:


    published_status(Video.first) # returns a string indicating whether the first video in the database is published or not

# **published_at function**

Description: This function returns a string representing the date and time at which a video was published, or "n/a" if the video is not published.

Input parameters:

video (object): An object representing a video. The object should have a published? method and a published_at attribute.
Output values:

A string representing the date and time at which the video was published, or "n/a" if the video is not published.
Error conditions:

If the video parameter is nil, the function returns nil.
Examples of usage:


    published_at(Video.first) # returns a string representing the date and time at which the first video in the database was published, or "n/a" if the video is not published


# **organisation_name function**

Description: This function returns the name of the organisation associated with a video, or "Vista" if the video is not associated with an organisation.

Input parameters:

video (object): An object representing a video. The object should have an organisation attribute.
Output values:

The name of the organisation associated with the video, or "Vista" if the video is not associated with an organisation.
Error conditions:

If the video parameter is nil, the function returns nil.
Examples of usage:


    organisation_name(Video.first) # returns the name of the organisation associated with the first video in the database, or "Vista" if the video is not associated with an organisation

# **organisation_select function**

Description: This function generates an array of arrays containing the names and IDs of all organisations, with "Vista" included as the first option.

Input parameters:

None.
Output values:

An array of arrays containing the names and IDs of all organisations, with "Vista" included as the first option.
Error conditions:

None.
Examples of usage:


    organisation_select # returns an array of arrays containing the names and IDs of all organisations, with "Vista" included as the first option