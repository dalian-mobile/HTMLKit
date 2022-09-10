# Templating

## Overview

### Embed

You can embed the view in the page structure.

```swift
struct SimplePage: Page {

    var body: AnyContent {
        Document(type: .html5)
        Head {
            Title {
                "SimplePage"
            }
        }
        Body {
            SimpleView(context: "Hello World!")
        }
    }
}
```

### Extend

You can extend the page in the view structure.

```swift
struct IndexView: View {

    var body: AnyContent {
        SimplePage {
            Heading1 {
                "Hello World!"
            }
        }
    }
}
```

### Output

```html
<!DOCTYPE html> 
<html>
    <head>
        <title>SimplePage</title>
    </head>
    <body>
        <h1>Hello World!</h1>
    </body>
</html>
```