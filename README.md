# Java-Algorithms
### Получение пропорциональных значений при сжатие прямоугольника, картинки
```Java
int width = 1920;                                                             // начальный width
int height = 1080;                                                            // начальный height

int maxWidth = 300;                                                           // устанавливаем макс. допустимый width 
int maxHeight = 200;                                                          // устанавливаем макс. допустимый height

double k = Math.max((double) width / maxWidth, (double) height / maxHeight);  // находим коэфициент сжатия
width = (int) (width / k);                                                    // получаем новый width
height = (int) (height / k);                                                  // получаем новый height
```
