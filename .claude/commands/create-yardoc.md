I want you to act as a YARD documentation expert for Ruby on Rails. Analyze my Ruby code and create comprehensive YARD-compliant documentation for it. Follow these specific guidelines:

## General Requirements
- Use YARD syntax instead of traditional RDoc syntax
- Use @-directives instead of RDoc's :-directives
- Document every class, module, method, and significant block in the code
- Maintain consistency in documentation style
- **Important:** Generate all documentation in English
- **Critical:** If documentation already exists, preserve it by rephrasing rather than deleting it completely
- When converting existing comments to YARD format, retain the original meaning and content while adding the proper YARD syntax

## Specific Elements to Document
1. **Class Descriptions**:
   - Start with a general description of the class and its purpose

2. **Methods**:
   - Clearly describe what the method does
   - Use `@param [Type] name description` for all parameters
   - Use `@option params [Type] name description` for hash parameters
   - Use `@return [Type] description` for the return value
   - Use `@raise [ExceptionClass] description` for possible exceptions
   - Use `@example` with code examples for complex methods
   - Use `@see` for cross-references to other relevant methods or classes
   - Use `@deprecated` with an explanation for deprecated methods

3. **Attributes**:
   - Document all `attr_accessor`, `attr_reader`, and `attr_writer` with `@attr`, `@attr_reader`, or `@attr_writer`
   - Specify type and description: `@attr [Type] name description`

4. **Modules and Mixins**:
   - Explain the purpose of the module and how it should be used
   - Document which methods are added by the mixin

5. **Advanced Techniques**:
   - Use `@!parse` for methods that are dynamically generated
   - Use `@!attribute` for more complex attributes
   - Use `@!method` for dynamically defined methods
   - Use `@overload` for methods with different parameter signatures

6. **Private Code**:
   - Document private methods as well, but clearly mark them as private
   - Explain why and how these methods are used internally

## Example Format

Here are examples of the expected documentation:

**Example for a method:**

```ruby
# Loads user data from the database and prepares it for display
#
# @param [Integer] user_id The ID of the user to load
# @param [Hash] options Additional options for loading
# @option options [Boolean] :include_posts Whether to include user posts (default: false)
# @option options [Integer] :limit Maximum number of posts to load (if include_posts is true)
#
# @return [User, nil] The loaded user or nil if not found
#
# @raise [DatabaseError] If the database connection fails
#
# @example Loading a user with their 5 most recent posts
#   load_user(123, include_posts: true, limit: 5)
#
# @see User
# @see Post
def load_user(user_id, options = {})
  # Implementation...
end
```

**Example for a controller action:**

```ruby
# Lists all documents available to the current user
#
# @url /documents
# @action GET
#
# @param [Hash] params Request parameters
# @option params [Integer] :page The page number for pagination (default: 1)
# @option params [Integer] :per_page Number of items per page (default: 20)
# @option params [String] :sort_by Field to sort by (default: 'created_at')
# @option params [String] :order Sort direction, 'asc' or 'desc' (default: 'desc')
#
# @return [Array<Document>] List of document objects
# @raise [AuthorizationError] If user doesn't have permission to list documents
def index
  # Implementation...
end
```

## Special Instructions

- Structure the documentation so it can be easily generated with `yard` or `yard doc`
- Consider Rails-specific conventions like Active Record associations, callbacks, and validations
- Document API endpoints, controller actions, and their parameters thoroughly
- For controllers, include URL and action information using:
  - `@url [path]` to indicate the route path (e.g., `@url /documents`)
  - `@action [HTTP_METHOD]` to indicate the HTTP method (e.g., `@action GET`)
- Use tags like `@todo` for pending implementations or improvements

Please analyze my code and create complete YARD documentation following these guidelines, which I can directly insert into my code. When processing existing code with comments, always preserve the existing documentation content by rephrasing it to fit the YARD format rather than replacing it entirely. Maintain the original meaning and intent of all existing comments.
