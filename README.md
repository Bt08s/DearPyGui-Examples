# Primary window with blue theme
![image](https://github.com/Bt08s/DearPyGui-Examples/assets/68190921/e76b9bf8-86e1-4bfc-ad44-092392032741)
```python
import dearpygui.dearpygui as dpg


def create_window():
    with dpg.window(tag="Primary Window"):
        dpg.add_button(label="Button", width=80)
        dpg.add_checkbox(label="Checkbox")


def set_global_theme():
    with dpg.theme() as global_theme:
        with dpg.theme_component(dpg.mvAll):
            dpg.add_theme_style(dpg.mvStyleVar_WindowRounding, 3)
            dpg.add_theme_style(dpg.mvStyleVar_FrameRounding, 3)
            dpg.add_theme_style(dpg.mvStyleVar_GrabRounding, 3)
            dpg.add_theme_style(dpg.mvStyleVar_TabRounding, 3)
            dpg.add_theme_style(dpg.mvStyleVar_ChildRounding, 3)
            dpg.add_theme_style(dpg.mvStyleVar_PopupRounding, 3)
            dpg.add_theme_style(dpg.mvStyleVar_ScrollbarRounding, 3)
            dpg.add_theme_style(dpg.mvStyleVar_FramePadding, 6, 6)

            dpg.add_theme_color(dpg.mvThemeCol_WindowBg, (21, 22, 23))
            dpg.add_theme_color(dpg.mvThemeCol_FrameBg, (32, 50, 77))
            dpg.add_theme_color(dpg.mvThemeCol_Button, (39, 73, 114))
            dpg.add_theme_color(dpg.mvThemeCol_FrameBg, (32, 50, 77))

    dpg.bind_theme(global_theme)


if __name__ == "__main__":
    dpg.create_context()

    set_global_theme()
    create_window()

    dpg.create_viewport(title='Custom Title', width=600, height=200, clear_color=(115, 140, 152))
    dpg.setup_dearpygui()
    dpg.show_viewport()
    dpg.set_primary_window("Primary Window", True)
    dpg.start_dearpygui()
    dpg.destroy_context()
```

# Red theme
![image](https://github.com/Bt08s/DearPyGui-Examples/assets/68190921/bd142782-7c77-415c-8fb8-1cd4a9329a35)
```python
def set_global_theme():
    with dpg.theme() as global_theme:
        with dpg.theme_component(dpg.mvAll):
            dpg.add_theme_style(dpg.mvStyleVar_WindowRounding, 5)
            dpg.add_theme_style(dpg.mvStyleVar_FrameRounding, 4)
            dpg.add_theme_style(dpg.mvStyleVar_GrabRounding, 5)
            dpg.add_theme_style(dpg.mvStyleVar_TabRounding, 5)
            dpg.add_theme_style(dpg.mvStyleVar_ChildRounding, 5)
            dpg.add_theme_style(dpg.mvStyleVar_PopupRounding, 5)
            dpg.add_theme_style(dpg.mvStyleVar_ScrollbarRounding, 5)
            dpg.add_theme_style(dpg.mvStyleVar_FramePadding, 5, 5)
            dpg.add_theme_style(dpg.mvStyleVar_ItemSpacing, 5, 5)
    
            dpg.add_theme_color(dpg.mvThemeCol_WindowBg, (28, 30, 31))
            dpg.add_theme_color(dpg.mvThemeCol_FrameBg, (84, 51, 51))
            dpg.add_theme_color(dpg.mvThemeCol_Button, (88, 47, 47))
            dpg.add_theme_color(dpg.mvThemeCol_TitleBgActive, (84, 51, 51))

    dpg.bind_theme(global_theme)
```

# Child window
![image](https://github.com/Bt08s/DearPyGui-Examples/assets/68190921/70d631d3-7745-40b8-92c2-028ba1fd2760)
```python
def create_window():
    with dpg.window(tag="Primary Window"):
        with dpg.child_window(height=100, width=200):
            dpg.add_text("Hello, world")
```

# Space
```python
dpg.add_spacing(count=10)
```

# Tab
![image](https://github.com/Bt08s/DearPyGui-Examples/assets/68190921/fb154e78-6144-4f27-a067-924f8939bd53)
```python
with dpg.tab_bar():
    with dpg.tab(label="Tab1"):
        dpg.add_text("Tab1 text")
    with dpg.tab(label="Tab2"):
        dpg.add_text("Tab2 text")
```

# Multiple windows
![image](https://github.com/Bt08s/DearPyGui-Examples/assets/68190921/e626fefc-2260-4053-9a25-f95024912c02)
```python
def create_window1():
    with dpg.window(label="Window 1"):
        dpg.add_text("win1 text")

def create_window2():
    with dpg.window(label="Window 2", no_title_bar=True, pos=(100, 50)):
        dpg.add_text("win2 text")
```

# File dialog (select directory)
![image](https://github.com/Bt08s/DearPyGui-Examples/assets/68190921/5733b804-0774-4ab4-a6ca-99ccb57a0caa)
```python
def select_directory(sender, app_data):
    global file_path
    file_path = app_data.get("file_path_name")
    print(file_path)

def create_window():
    with dpg.window(tag="Primary Window"):
        dpg.add_button(label="Select dir", width=100, callback=lambda: dpg.show_item("file_dialog"))
        dpg.add_file_dialog(directory_selector=True, show=False, tag="file_dialog", height=250, width=400, callback=select_directory)
```

# Drag and drop
![image](https://github.com/Bt08s/DearPyGui-Examples/assets/68190921/b5bb8bb4-13d3-49c0-bd12-2472012f92a1)
```python
import DearPyGui_DragAndDrop as dpg_dnd
import dearpygui.dearpygui as dpg


def create_window():
    global drop_text, drop_keys
    with dpg.window(tag="Primary Window"):
        drop_text = dpg.add_text()
        drop_keys = dpg.add_text()


def set_global_theme():
    with dpg.theme() as global_theme:
        with dpg.theme_component(dpg.mvAll):
            dpg.add_theme_style(dpg.mvStyleVar_WindowRounding, 5)
            dpg.add_theme_style(dpg.mvStyleVar_FrameRounding, 5)
            dpg.add_theme_style(dpg.mvStyleVar_GrabRounding, 5)
            dpg.add_theme_style(dpg.mvStyleVar_TabRounding, 5)
            dpg.add_theme_style(dpg.mvStyleVar_ChildRounding, 5)
            dpg.add_theme_style(dpg.mvStyleVar_PopupRounding, 5)
            dpg.add_theme_style(dpg.mvStyleVar_ScrollbarRounding, 5)
            dpg.add_theme_style(dpg.mvStyleVar_FramePadding, 5, 5)
            dpg.add_theme_style(dpg.mvStyleVar_ItemSpacing, 5, 5)

            dpg.add_theme_color(dpg.mvThemeCol_WindowBg, (21, 22, 23))
            dpg.add_theme_color(dpg.mvThemeCol_FrameBg, (32, 50, 77))
            dpg.add_theme_color(dpg.mvThemeCol_Button, (39, 73, 114))
            dpg.add_theme_color(dpg.mvThemeCol_FrameBg, (32, 50, 77))

    dpg.bind_theme(global_theme)


def drop(data, keys):
    dpg.set_value(drop_text, f'{data}')


if __name__ == "__main__":
    dpg.create_context()
    dpg_dnd.initialize()
    dpg_dnd.set_drop(drop)

    create_window()
    set_global_theme()

    dpg.create_viewport(title='Custom Title', width=600, height=200, clear_color=(115, 140, 152))
    dpg.setup_dearpygui()
    dpg.show_viewport()
    dpg.set_primary_window("Primary Window", True)
    dpg.start_dearpygui()
    dpg.destroy_context()
```

# Non decorated window (without viewport title bar)
```python
dpg.create_viewport(title='Custom Title', width=600, height=200, clear_color=(115, 140, 152), decorated=False)
```

# Popup (simple messagebox)
![image](https://github.com/Bt08s/DearPyGui-Examples/assets/68190921/58ab0b96-6378-44b2-8183-bd57ff32d25e)
```python
def show_popup():
    dpg.set_value("popup_text", "This is a popup")
    dpg.show_item("popup")

def create_window():
    with dpg.window(tag="Primary Window"):
        dpg.add_button(label="Show popup", width=100, callback=show_popup)
        with dpg.popup(dpg.last_item(), modal=True, tag="popup"):
            dpg.add_text(tag="popup_text")
```

Other DPG stuffs:
* https://github.com/DataExplorerUser/autoscroll/blob/main/autoscroll.py
* https://github.com/fabriciochamon/DearPyGui_Extend#file-browser
* https://github.com/my1e5/dpg-examples/blob/main/misc/date_picker.py
* https://github.com/IvanNazaruk/DearPyGui-Markdown

Other GUI stuffs:
* https://pypi.org/project/messagebox
* https://pypi.org/project/windows_filedialogs
