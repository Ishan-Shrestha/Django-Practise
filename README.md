# Django Learning Journey

A personal project to learn Django web framework by following the official Django documentation.

## Credit
This project follows the [Official Django Tutorial](https://docs.djangoproject.com/en/stable/intro/tutorial01/) from the Django Documentation.

## Learning Progress

### ✅ Part 1: Requests and Responses

**Key Concepts Learned:**
- Creating a Django project with `django-admin startproject`
- Creating apps with `python manage.py startapp`
- Understanding project structure (manage.py, settings.py, urls.py)
- Writing first view (basic HttpResponse)
- URL routing and URLconf
- Connecting app URLs to project URLs using `include()`
- Running the development server

**Key Takeaways:**
- A Django project can contain multiple apps
- Apps are reusable components with specific functionality
- Views are Python functions that handle requests and return responses
- URLs map web addresses to views

---

### ✅ Part 2: Models and the Admin Site

**Key Concepts Learned:**
- Defining models (Question and Choice models)
- Understanding fields (CharField, DateTimeField, IntegerField, ForeignKey)
- Database relationships (ForeignKey creates one-to-many relationships)
- Activating models by adding app to `INSTALLED_APPS`
- Database migrations:
  - `makemigrations` - creates migration files
  - `migrate` - applies changes to database
  - `sqlmigrate` - shows SQL for migrations
- Django shell for interacting with database
- Model methods and the `__str__()` method
- Django's automatic reverse relationships (`choice_set`)
- Creating a superuser
- Registering models in admin with `admin.site.register()`
- Using Django's admin interface

**Key Takeaways:**
- Models define your database structure using Python classes
- ForeignKey creates relationships; Django auto-creates reverse access with `modelname_set`
- Migrations are Django's way of propagating model changes to the database
- Django admin provides a powerful interface for managing data

---

### ✅ Part 3: Views and Templates\

**Key Concepts Learned:**
- Creating templates in `app/templates/app/` directory structure
- Template namespacing to avoid naming conflicts
- Django template language:
  - Variables: `{{ variable }}`
  - Tags: `{% if %}`, `{% for %}`, `{% url %}`
  - Filters and logic in templates
- The `render()` shortcut function
- Passing context (data) from views to templates
- Template variable access with dot notation (e.g., `question.question_text`)
- Error handling with `Http404` and `get_object_or_404()`
- Accessing related objects in templates (e.g., `question.choice_set.all`)
- Removing hardcoded URLs using the `{% url %}` template tag
- URL namespacing with `app_name` in URLconf
- Using namespaced URLs: `{% url 'polls:detail' question.id %}`

**Key Takeaways:**
- Templates separate presentation (HTML) from logic (Python)
- Context is a dictionary of data passed from views to templates
- Always use `{% url %}` instead of hardcoding URLs for maintainability
- Template namespacing prevents conflicts between apps
- Django automatically creates reverse relationships (e.g., `question.choice_set`)
- String formatting with `%s` vs modern f-strings

---

### ⬜ Part 4: Forms and Generic Views
**Status:** Not started

**Topics to Cover:**
- Writing a simple form
- Using generic views
- Reducing code with generic views

---

### ⬜ Part 5: Testing
**Status:** Not started

**Topics to Cover:**
- Automated testing
- Writing tests for models and views
- Test-driven development

---

### ⬜ Part 6: Static Files
**Status:** Not started

**Topics to Cover:**
- Adding stylesheets and images
- Static files configuration

---

### ⬜ Part 7: Customizing the Admin Site
**Status:** Not started

**Topics to Cover:**
- Customizing admin forms
- Adding related objects
- Customizing admin change list
- Customizing admin look and feel

---

## Project Structure
```
mysite/
    manage.py
    mysite/
        __init__.py
        settings.py
        urls.py
        asgi.py
        wsgi.py
    polls/
        __init__.py
        admin.py
        apps.py
        migrations/
        models.py
        tests.py
        views.py
        urls.py
        templates/
            polls/
                index.html
                detail.html
```

## Commands Reference

### Project Setup
```bash
# Create new project
django-admin startproject projectname

# Create new app
python manage.py startapp appname

# Run development server
python manage.py runserver
```

### Database & Models
```bash
# Create migration files
python manage.py makemigrations

# Apply migrations
python manage.py migrate

# View SQL for migration
python manage.py sqlmigrate appname migration_number

# Open Django shell
python manage.py shell
```

### Admin
```bash
# Create superuser
python manage.py createsuperuser
```

## Key Learnings & Notes

### Understanding Django's MTV Pattern
- **Model:** Defines data structure (database schema)
- **Template:** Presentation layer (HTML)
- **View:** Business logic (connects models and templates)

### Important Concepts
- **Apps vs Projects:** A project contains multiple apps; apps are reusable components
- **Settings.py:** Central configuration file (rules for the project)
- **ForeignKey Relationships:** Creates connections between models; Django auto-generates reverse relationships
- **Migrations:** Version control for your database schema
- **Templates:** HTML files that use Django template language to display dynamic data
- **Context:** Dictionary of data passed from views to templates
- **URL Patterns:** Use `<int:variable>` to capture URL parts and pass them to views
- **Named URLs:** Reference URLs by name instead of hardcoding paths for maintainability

### Tips
- Follow the tutorial linearly - don't get lost in documentation links
- Type code yourself rather than copy-pasting
- Read error messages carefully - Django's errors are helpful
- Use `python manage.py shell` to experiment with models

---

## Next Steps
- [x] Complete Part 3 of the tutorial ✅
- [ ] Complete Part 4 of the tutorial
- [ ] Build a simple personal project to reinforce learning
- [ ] Explore Django REST Framework (after completing basic tutorial)

## Resources
- [Django Documentation](https://docs.djangoproject.com/)
- [Django Tutorial](https://docs.djangoproject.com/en/stable/intro/tutorial01/)
- [Django REST Framework](https://www.django-rest-framework.org/) (for later)

---

*Last Updated: January 23, 2026*