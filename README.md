# Primary window with blue theme
![image](https://github.com/Bt08s/DearPyGui-Examples/assets/68190921/d43da6a8-bb86-426e-b3d0-78b03a3cd23e)
```python
import dearpygui.dearpygui as dpg


def create_window():
    with dpg.window(tag="Primary Window"):
        dpg.add_button(label="Button", width=75)
        dpg.add_checkbox(label="Checkbox")
        dpg.add_text("Hello, world")


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

# File dialog
![image](https://github.com/Bt08s/DearPyGui-Examples/assets/68190921/b7260cda-9847-4e89-8ea2-6e712df7b9e8)
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
