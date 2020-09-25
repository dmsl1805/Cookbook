# Headway iOS cookbook 
Let’s begin a series of tips how we write code, define components and work with dependencies.

### Chapter 1. 
Start with the view controller. 
```swift
import UIKit

final class SearchViewController: DisposeContainer {
    @IBOutlet private(set) var searchTextField: UITextField!
    @IBOutlet private(set) var segmentedControl: UISegmentedControl!
    @IBOutlet private(set) var tableView: UITableView!
}
```

And a simple protocol.
```swift
import RxSwift

protocol DisposeContainer {
    var bag: DisposeBag { get }
}
```
> There will be no code added inside this view controller, not even in extension, I promise😉

Interesting how? Continue reading.














Chapter 2. Drive. 
We use “drivers” to define and manipulate state. It can be a shared app component state or a simple view state. Equivalent to ViewModel in well known mvvm.

Next I will show how to bind our ViewController with the Driver.





















Chapter 3. Binder. 
Here is a definition of ViewControllerBinder protocol. It is so common to touch the view of the view controller inside of the “viewDidLoad”. There are rare cases where we use a different approach, but the current one suits 99% of the time.
-
And how actual logic can be implemented.
-
Style from config
State binding
Actions binding
-
Want even more separation of UI logic? Look further.



Chapter 3. Cut into pieces. Our binder actually do 3 main things:
Fills the UI from static config.
Binds Driver state to the UI .
Binds actions taken from view to Driver’s actions.
Let’s try to break it to even simpler components
Config binder
State binder
Action binder
Got code, but not the working app. Let’s fix it next.



Chapter 4. The DI principles we use at Headway are simple:
implementation knows only interface
only Factory knows about others and other Factories

Chapter 5. Additional components - Analytics:

Chapter 6 unowned closure bindings

