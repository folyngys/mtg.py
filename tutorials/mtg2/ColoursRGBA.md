## mtg2.ColoursRGBA()
### Описание
Класс [mtg2.ColoursRGBA](https://github.com/romanin-rf/mtg.py/blob/main/tutorials/mtg2/ColoursRGBA.md), нечего не принимает. Сделан для конвертации данных из под класса [mtg2.ColourRGBA](https://github.com/romanin-rf/mtg.py/blob/main/tutorials/mtg2/ColourRGBA.md).

### Пример
```python
>>> import mtg2
>>> mtg2.ColoursRGBA()
ColoursRGBA('white', 'black', 'red', 'green', 'blue', 'yellow', 'orange', 'pink', 'purple', 'cyan', 'gold', 'marine', 'brown')
>>> mtg2.ColoursRGBA()["black"]
(0, 0, 0, 255)
```

### Функции
- [mtg2.ColoursRGBA.is_rgba](https://github.com/romanin-rf/mtg.py/blob/main/tutorials/mtg2/ColoursRGBA.md#mtg2coloursrgbais_rgba)
- mtg2.ColoursRGBA.hex_to_rgba
- mtg2.ColoursRGBA.get_colour_type
- mtg2.ColoursRGBA.get_colour
- mtg2.ColoursRGBA.set_colour
- mtg2.ColoursRGBA.set_colours

<hr>

## mtg2.ColoursRGBA().is_rgba
### Описание
Функция примичает `colour` в виде ***tuple[int, int, int, int]*** и проверяет являеться ли он `rgba-цветом`, и возвращает ***bool***.
```python
mtg2.ColoursRGBA.is_rgba(colour: tuple[int, int, int, int]) -> bool
```
### Пример
```python
>>> import mtg2
>>> mtg2.ColoursRGBA().is_rgba((0, 255, 183, 185))
True
>>> mtg2.ColoursRGBA().is_rgba((256, 0, 128, 255))
False
```
## mtg2.ColoursRGBA().hex_to_rgba
### Описание
Функция примичает `colour` в виде ***str*** и конвертирует в `hex-цвет`, возращает `rgba-цвет` в виде ***tuple[int, int, int, int]***, в противном случае ***None***.
```python
mtg2.ColoursRGBA.hex_to_rgba(colour: str) -> tuple[int, int, int, int] | None:
```
### Пример
```python
>>> import mtg2
>>> mtg2.ColoursRGBA().hex_to_rgba("#ff0088ff")
(255, 0, 136, 255)
>>> mtg2.ColoursRGBA().hex_to_rgba("f8f")
(255, 136, 255, 255)
>>> mtg2.ColoursRGBA().hex_to_rgba("ff0ff")
None
```
## mtg2.ColoursRGBA().get_colour_type
### Описание
Функция принимает `colour` в виде ***str*** или ***tuple[int, int, int, int]*** и возвращает `тип цвета` в виде `str`:
- 'rgba-colour'
    - это тип цвета в виде ***tuple[int, int, int, int]***
- 'hex-colour'
    - это тип цвета в виде ***str*** ([пример выше]())
- 'name-colour'
    - это тип цвета, являеться `name` в классе [mtg2.ColoursRGBA](https://github.com/romanin-rf/mtg.py/blob/main/tutorials/mtg2/ColoursRGBA.md#пример)

<br>

В противном случае выводит ***None***.
```python
mtg2.ColoursRGBA.get_colour_type(colour: str | tuple[int, int, int, int]) -> Literal['rgba-colour', 'hex-colour', 'name-colour'] | None
```
### Пример
```python
>>> import mtg2
>>> mtg2.ColoursRGBA().get_colour_type("ff0088")
'hex-colour'
>>> mtg2.ColoursRGBA().get_colour_type("black")
'name-colour'
>>> mtg2.ColoursRGBA().get_colour_type((255, 55, 0, 78))
'rgba-colour'
>>> mtg2.ColoursRGBA().get_colour_type("f80f1")
None
```
