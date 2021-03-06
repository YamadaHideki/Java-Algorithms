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
### Алгоритм перемешивания массива
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
### Алгоритм поиска недостающего элемента в перемешанном массиве с целыми числами (Standart)
```Java
public long searchMissingNumberBase() {
        long originSum = (size + 1) * (size + 2) / 2;           // подсчет суммы значений в до потери числа
        long actualSum = 0;                                     // сохранение суммы значений в массиве с потерей числа  
        
        for (long i : array) {
            actualSum += i;
        }

        return originSum - actualSum;
    }
```
### Алгоритм поиска недостающего элемента в перемешанном массиве с целыми числами (XOR)
```Java
public long searchMissingNumberXor() {
        long xor = 0;

        for (long i = 1; i < size + 2; i++) {           // все значения чисел который были в массиве
            xor ^= i;                                   // побитовое сравнение и присвоение изменения сравнения
        }

        for (long j = 0; j < size; j++) {               // значения чисел в массиве где пропало 1 число
            xor ^= array[(int) j];                      // побитовое сравнение и присвоение изменения сравнения
        }

        return xor;
    }
```
### Алгоритм нахождения максимального числа в отсортированном массиве со смещением (не работает без смещения)
```Java
int[] a = new int[] {3, 4, 5, 6, 7, 8, 9, 1, 2};
int left = 0;
int right = a.length - 1;

int nextEl;
int prevEl;

int max = 0;

while (left <= right) {
    int mid = (left + right) / 2;
    System.out.println("MID: " + mid);
    try {
        nextEl = a[mid + 1];
    } catch (ArrayIndexOutOfBoundsException e) {
        nextEl = a[0];
    }

    try {
        prevEl = a[mid - 1];
    } catch (ArrayIndexOutOfBoundsException e) {
        prevEl = a[a.length - 1];
    }

    if (a[mid] > nextEl && a[mid] > prevEl) {
        max = a[mid];
        break;
    }

    if (a[left] >= a[mid]) {
        right = mid - 1;
    } else {
        left = mid + 1;
    }
}

if (max == 0) {
    max = -1;
}
```
