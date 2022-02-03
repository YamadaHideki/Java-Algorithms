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
### Алгоритм сортировки массива
```Java
public void shuffle() {
        for (int i = 0; i < array.length; i++) {
            int randomPosition = (int) (Math.random() * (array.length - 1 - i));  // берем рандомный ключ массива
            int lastInt = array[array.length - 1 - i];                            // сохраняем результат последнего ключа массива
            array[array.length - 1 - i] = array[randomPosition];                  // в последнюю ячейку массива присваиваем значение из позиции randomPosition
            array[randomPosition] = lastInt;                                      // на место randomPosition кладем данные из последней ячейке массива сохр. в lastInt
        }
    }
```
