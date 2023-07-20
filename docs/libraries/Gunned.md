# GunnedTUI
This C++ library provides classes for creating TUI elements like buttons, labels, and input fields. These classes allow for quick and efficient building of user interfaces in a C++ environment 🔥.

Github Repository: [GunnedTUI](https://github.com/xauthorg/GunnedTUI)

### Classes
The library contains the following classes:

`Button` - Represents a button in a terminal user interface. It can be rendered, set to active/inactive, and has a unique identifier. <br/>
`Write` - Represents a static label in a graphical user interface. It can be rendered on the screen.<br/>
`Field` - Represents an interactive input field in a graphical user interface. It can be rendered, updated, and the value can be retrieved.<br/>

### Usage
Include the appropriate header file(s) in your C++ program to utilize these classes. Once included, you can construct instances of `Button`, `Write`, and `Field` by providing the required parameters. Each of these instances can be rendered to the screen.


## Examples:

### Here is how you would contruct a `Writer` element
Constructor and Methods:
```cpp
Write::Write(int x, int y, string label_){
        x_ = x
        y_ = y
        label_ = label
}

void Writer::render() const {
    std::cout << "\033[" << y_ << ";" << x_ << "H";
    std::cout << "\033[2K\033[1G";
    std::cout << label_ << std::endl;
}
```

Usage:
```cpp
int main() {
    Writer writer(1, 1, "My Label");
    writer.render();

    return 0;
}
```

The render function utilizes console escape sequences to move the cursor to the desired (x_, y_) coordinates, then clears the current line before writing the `label_`.<br/>

### Here is how you would contruct a `Button` element

Constructor and Methods:
```cpp
Button::Button(int id, int x, int y, string label, string description) {
	id_ = id;
	x_ = x;
	y_ = y;
	label_ = label;
	active_ = false;
    description_ = description;
}

void Button::setActive(bool active) {
    active_ = active;
}

int Button::getId() const {
    return id_;
}

void Button::render() const {
    int buttonWidth = label_.length();
    string horizontalLine(buttonWidth, '--');
    SetConsoleOutputCP(65001);
    if (active_) {
        if (label_.compare(" Exit ")) {
            cout << "\033[30;47m";
            Write::Write(1, 1, description_).render();
        }
        else {
            cout << "\033[37;41m";
            Write::Write(1, 1, description_).render(); 
        }
	}
    cout << "\033[" << y_ << ";" << x_ << "H";
    cout << "┌" << horizontalLine << "┐" << endl;
    cout << "\033[" << y_ + 1 << ";" << x_ << "H";
    cout << "│" << label_ << "│" << endl;
    cout << "\033[" << y_ + 2 << ";" << x_ << "H";
    cout << "└" << horizontalLine << "┘\033[0m" << endl;
}
```

Usage:

```cpp
int main() {
    std::vector<Button> buttons;
    buttons.push_back(Button(1, 4, 5, " Login ", "Login to your existing account"));
    buttons[0].setActive(true);

    for (const auto& button : buttons) {
        button.render();
    }

    return 0;
}
```
This example creates a `Button` instance with the label `" Login "` and description `"Login to your existing account"`. The button's position is set at (`4, 5`), and its unique ID is `1`. Afterward, we set this button as active and render it to the console.

### Here is how you would contruct a `Field` element
Constructor and Methods:
```cpp
Field::Field(int x, int y, std::string label, std::string value) {
    x_ = x;
    y_ = y;
    label_ = label;
    value_ = value;
}

void Field::render() const {
    size_t fieldLength = max(max(label_.size(), value_.size()), size_t(10));
    std::string horizontalLine(fieldLength + 2, '--');
    int padding = (fieldLength - value_.size()) / 2;
    int extra = (fieldLength - value_.size()) % 2+1;

    std::cout << "\033[" << y_ << ";" << x_ << "H";
    std::cout << "\033[0m┌" << horizontalLine << "┐" << std::endl;
    std::cout << "\033[" << y_ + 1 << ";" << x_ << "H";
    std::cout << "│" << std::string(padding, ' ') << " "+value_;
    std::cout << std::string(padding + extra, ' ');
    std::cout << "│" << std::endl;
    std::cout << "\033[" << y_ + 2 << ";" << x_ << "H";
    std::cout << "└" << horizontalLine << "┘\033[0m" << std::endl;
}

void Field::updateValue() {
    std::cout << "\033[" << y_ + 1 << ";" << x_ + 1 << "H";
    std::cout << "\033[K";
    std::string newValue;
    std::getline(std::cin, newValue);
    value_ = newValue;
    render();
}

std::string Field::getValue() const {
    return value_;
}
```
The `Field` constructor initializes its member variables. The render method displays the field's value centered within a box of dynamic size. The updateValue method reads new input from the user, updates the field's value, and re-renders the field. The getValue method returns the current `value_` of the field.

Usage:

```cpp
int main() {
    Field usernameField(2, 2, "Username", "");
    usernameField.render();
    usernameField.updateValue();
    usernameField.render();

    std::cout << "The entered username is: " << usernameField.getValue();

    return 0;
}
```
In this example, we create a `Field` instance for a username with an initial blank value. The position of the field is set at (`2, 2`). We render the field, accept user input to update the field's value, and display the current value to the console.

