I. How to use Rails helper
1. General
- Used in Rails view to share reusable code.
- Some methods:
  + time_ago_in_words.
  + number_to_human.
- Where?
  + app/helper
- Base helper: ApplicationHelper.
- Benefit: Don't have to repeat logic in views.

2. How to use helper methods in Controllers
- Rails version 4: Include the helper module.
- Rails version 5: Use with **helpers** object.

```
class UsersController < ApplicationController
  helpers.format_name(name)
end
```

3. How to use helper in Rails console
- Use with **helper** following the name of method.

4. Best practices
- Don't use instance varibles in helper, they may be available in your current view, but they may not be in another view. Therefore, it will result in an error because of missing variables.
  + Example:
  ```
  ** Bad **
  def eat_healthy
    @fruit.eat
  end

  * Good **
  def eat_healthy(fruit)
    fruit.eat
  end
  ```

- All helpers should have unique names.

==========================================================================================

II. Presenter objects
1. General
