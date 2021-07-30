#импорты
from kivy.app import App
from kivy.uix.button import Button
from kivy.config import Config
from kivy.uix.floatlayout import FloatLayout
from kivy.uix.codeinput import CodeInput
from pygments.lexers import HtmlLexer

#resizable что мы меняем/0 окно невозможно сделать на весь экран
Config.set('graphics', 'resizable', '0');
Config.set('graphics', 'width', '640');
Config.set('graphics', 'height', '480');
#Создание класса приложения
class MyApp(App):
    def build(self):

        fl = FloatLayout(size = (300, 300))
        fl.add_widget(Button(text = "My first button",
        font_size=30,
        on_press=self.btn_press,
        background_color=[.32, .85, .94, 1],
        background_normal='',
        size_hint = (.5, .25),
        pos = (0, 0)))
        return fl

    def btn_press(self, instance):
        print("Button is pressed")
        instance.text = "I am pressed"


if __name__ == "__main__":
    MyApp().run()
