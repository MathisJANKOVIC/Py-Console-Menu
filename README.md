# py-cli-menu
<img src="https://img.shields.io/badge/version-1.0-darkred" alt="Issues Badge"/>
<img src="https://img.shields.io/badge/python-3.10%20%7C%203.11%20%7C%203.12-blue" alt="Issues Badge"/>
<img src="https://img.shields.io/badge/platform-Windows%20%7C%20Linux%20%7C%20MacOS-lightgray"/>
<img src="https://img.shields.io/badge/license-MIT-yellow"/>
<img src="https://img.shields.io/github/contributors/MathisJANKOVIC/py-cli-menu?color=darkgreen"/>


py-cli-menu is a simple cross-plateform Python module that allows you to easilly create pretty custom menus in console. Customize the title, options, every colors and initial cursor position as you wish. Use arrows keys to navigate through the menu and enter key to select an option.

![menu screen](images/screen_menu.png)

## Setup
```
python -m pip install py-cli-menu
```
## Quickstart

```python
def menu(
    title: str | Sequence[str],
    options: list[str] | tuple[str, ...],
    cursor_color: str | tuple[int, int, int],
    title_color: (
        str | tuple[int, int, int] | None |
        Sequence[str | tuple[int, int, int] | None]
    ) = None,
    options_color: (
        str | tuple[int, int, int] | None |
        Sequence[str | tuple[int, int, int] | None]
    ) = None,
    initial_cursor_position: int = 0,
) -> int:
```
> Creates a console GUI menu with arrow key navigation and returns the selected option. Clears console once an option is selected.

- `title` is the main title of the menu, can be displayed on multiple lines if a list or a tuple is passed
- `options` is the list of actions or choices that can be selected
- `cursor_color` is the color of the cursor, available colors are `red`, `green`, `yellow`, `blue`, `magenta`, `cyan` and `white`, use custom color by providing a tuple containing color RGB values
- `intial_cursor_position` is the index of the element or the element in `options` where the initial cursor position is set (default position is first element)
- `output_format` is the output type of the function, default is `str`, which returns the selected element from `options`, pass `int` to get the index of the selected element

<label style="font-size: 15px;">Examples :</label>

```python
from console_menu import menu

OPTIONS = ["Option 1", "Option 2", "Option 3", "Quit"]

# Creates a console menu with blue cursor and title on single line
choice1: str = menu("Amazing Console Menu", OPTIONS, "blue")

# Creates a console menu with orange cursor and title on multiple lines
choice2: str = menu(["Amazing Console", "Menu"], OPTIONS, (255, 102, 0))

# Creates a console menu with red cursor default set on last option
choice3: str = menu("Amazing Console Menu", OPTIONS, "red", initial_cursor_position=-1)

# Creates a console menu with yellow cursor and returns the index of selected option
choice4: int = menu("Amazing Console Menu", OPTIONS, "yellow", ouput_format=int)
```
