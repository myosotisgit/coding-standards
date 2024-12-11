# Coding standards Myosotis

Coding standards and naming conventions used by Myosotis.
These standards are based on the PHP, Laravel and Vue3 recommendations.

* php - https://github.com/php/php-src/blob/master/CODING_STANDARDS.md
* PSR-12 - https://www.php-fig.org/psr/psr-12/
* php FIG - https://www.php-fig.org/bylaws/psr-naming-conventions/
* Laravel - https://laravel.com/docs/11.x/contributions#coding-style
* Vue3 - https://vuejs.org/style-guide/
* Spatie.be - https://spatie.be/guidelines/laravel-php#content-views

# INDEX
* [Folders](https://github.com/myosotisgit/coding-standards#folders)
* [Files](https://github.com/myosotisgit/coding-standards#files)
* [Components](https://github.com/myosotisgit/coding-standards#components)
* [Vue Props](https://github.com/myosotisgit/coding-standards#props)
* [Arguments](https://github.com/myosotisgit/coding-standards#arguments)
* [Variables](https://github.com/myosotisgit/coding-standards#variables)

# Folders

### Project (root) folders: lowercase

> Laravel
```
app/
config/
resources/js/
storage/logs/
```

### child folders : PascalCase or lowercase
> Laravel

When a folder is referring to a component/model/class it uses PascalCase
```
app/Actions/
app/Console/
resources/js/components/Modals/
```

For other folders, not referring to model/class it uses lowercase
```
database/factories/
resources/js/components/
```
# Files

### File names: PascalCase / lowercase
> Laravel
When a file is referring to a model/class it uses PascalCase
```
app/Actions/CreateNewUser.php
app/Console/Kernel.php
```
For other folders, not referring to model/class it uses lowercase
```
config/broadcasting.php
```

# Components

## Components - PascalCase

> Filenames of Single-File Components should either be always PascalCase or always kebab-case.

> ALERT: Component names MUST BE multi-worded. This is to avoid possible confusion with html elements, which are always single-worded

```
Bad: <Modal />
Good: <ConfirmModal />
```

### Base Componentns

Base components (a.k.a. presentational, dumb, or pure components) that apply app-specific styling and conventions should all begin with a specific prefix, such as Base, App, or V.

```
<BaseModal />
```

### Tightly coupled component names​
Child components that are tightly coupled with their parent should include the parent component name as a prefix.

```
components/TodoList/
- TodoList.vue
- TodoListItem.vue
- TodoListItemButton.vue
```

### Order of words in component names​
Component names should start with the highest-level (often most general) words and end with descriptive modifying words.

```
- BaseModal
- ModalConfirm
- ModalConfirmButtons
```

### Self-closing components​
Components with no content should be self-closing in Single-File Components, string templates, and JSX - but never in in-DOM templates.

```
<ModalConfirm />
```

# Props 
## VUE - camelCase

### Use detailed prop definitions​
In committed code, prop definitions should always be as detailed as possible, specifying at least type(s).
```
const props = defineProps({
  status: String
})
```

### Prop names
Prop names should always use camelCase during declaration. When used inside in-DOM templates, props should be kebab-cased. Single-File Components templates and JSX can use either kebab-case or camelCase props.

```
const props = defineProps({
  greetingText: String
})

// for SFC - use consistent casing
<WelcomeMessage greeting-text="hi"/>
// or
<WelcomeMessage greetingText="hi"/>
```

### Multi-attribute elements​
Elements with multiple attributes should span multiple lines, with one attribute per line.
> Use prettier in VS Code
```
<MyComponent
  foo="a"
  bar="b"
  baz="c"
/>
```

# Variables

## Javascript
```
JS: camelCase
.env : SCREAMING_SNAKE_CASE
```

## Boostrap / CSS id, classes: kebab-case

```
class="custom-control-label my-auto"
```