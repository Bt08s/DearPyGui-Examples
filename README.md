# Primary window, blue theme
```python
import dearpygui.dearpygui as dpg


def create_main_window():
    with dpg.window(tag="Primary Window"):
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
    create_main_window()

    dpg.create_viewport(title='Custom Title', width=600, height=200)
    dpg.setup_dearpygui()
    dpg.show_viewport()
    dpg.set_primary_window("Primary Window", True) # Make window primary
    dpg.start_dearpygui()
    dpg.destroy_context()
```
![image](https://github.com/Bt08s/DearPyGui-Examples/assets/68190921/d43da6a8-bb86-426e-b3d0-78b03a3cd23e)

# Red theme
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
![image](https://github.com/Bt08s/DearPyGui-Examples/assets/68190921/bd142782-7c77-415c-8fb8-1cd4a9329a35)
