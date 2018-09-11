---
title: 'Пошаговое руководство: Умножение матриц | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 61172e8b-da71-4200-a462-ff3a908ab0cf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3aaf94bbe94dda019cc585b82744dbdf2332ffab
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42604494"
---
# <a name="walkthrough-matrix-multiplication"></a>Пошаговое руководство. Умножение матриц
Это пошаговое руководство демонстрирует использование C++ AMP для ускорения выполнения Перемножение матриц. Появится два алгоритма и один без заполнения с мозаичное заполнение.  
  
## <a name="prerequisites"></a>Предварительные требования  
 
Перед началом работы  
  
- Чтение [Обзор C++ AMP](../../parallel/amp/cpp-amp-overview.md).  
  
- Чтение [с помощью плитки](../../parallel/amp/using-tiles.md).  
  
- Убедитесь, что Windows 7, Windows 8, Windows Server 2008 R2 или Windows Server 2012 устанавливается на компьютере.  
  
### <a name="to-create-the-project"></a>Создание проекта  
  
1. В строке меню в Visual Studio, выберите **файл** > **New** > **проекта**.  
  
2. В разделе **установленные** в области «Шаблоны» выберите **Visual C++**.  
  
3. Выберите **пустой проект**, введите `MatrixMultiply` в **имя** поле, а затем выберите **ОК** кнопки.  
  
4. Нажмите кнопку **Далее**.  
  
5. В **обозревателе решений**, откройте контекстное меню для **исходные файлы**, а затем выберите **добавить** > **новый элемент**.  
  
6. В **Добавление нового элемента** выберите **файл C++ (.cpp)**, введите `MatrixMultiply.cpp` в **имя** поле, а затем выберите **добавить** кнопка.  
  
## <a name="multiplication-without-tiling"></a>Умножение без заполнения  
 
В этом разделе описано рассмотрим умножения двух матриц, А и Б, которые определяются следующим образом:  
  
![3&#45;по&#45;2 матрицы](../../parallel/amp/media/campmatrixanontiled.png "campmatrixanontiled")  
  
![2&#45;по&#45;3 матрицы](../../parallel/amp/media/campmatrixbnontiled.png "campmatrixbnontiled")  
  
Объект является матрицу 3 x 2, а B — матрица 2 x 3. Результат умножения A, B является следующая матрица 3 x 3. Продукт вычисляется путем умножения строки типа по столбцам B поэлементно.  
  
![3&#45;по&#45;3 матрицы](../../parallel/amp/media/campmatrixproductnontiled.png "campmatrixproductnontiled")  
  
### <a name="to-multiply-without-using-c-amp"></a>Для умножения без использования C++ AMP  
  
1. Откройте MatrixMultiply.cpp и используйте следующий код, чтобы заменить существующий код.  
  
```cpp  
#include <iostream>  
  
void MultiplyWithOutAMP() {  
    int aMatrix[3][2] = {{1, 4}, {2, 5}, {3, 6}};  
    int bMatrix[2][3] = {{7, 8, 9}, {10, 11, 12}};  
    int product[3][3] = {{0, 0, 0}, {0, 0, 0}, {0, 0, 0}};  
  
    for (int row = 0; row < 3; row++) {  
        for (int col = 0; col < 3; col++) {  
            // Multiply the row of A by the column of B to get the row, column of product.  
            for (int inner = 0; inner < 2; inner++) {  
                product[row][col] += aMatrix[row][inner] * bMatrix[inner][col];  
            }  
            std::cout << product[row][col] << "  ";  
        }  
        std::cout << "\n";  
    }  
}  
  
void main() {  
    MultiplyWithOutAMP();  
    getchar();  
}  
```  
  
    The algorithm is a straightforward implementation of the definition of matrix multiplication. It does not use any parallel or threaded algorithms to reduce the computation time.  
  
2. В строке меню выберите **Файл** > **Сохранить все**.  
  
3. Выберите **F5** сочетания клавиш, чтобы начать отладку и проверьте, правильно ли выходные данные.  
  
4. Выберите **ввод** выход из приложения.  
  
### <a name="to-multiply-by-using-c-amp"></a>Умножение с помощью C++ AMP  
  
1. В MatrixMultiply.cpp, добавьте следующий код перед `main` метод.  
  
```cpp  
void MultiplyWithAMP() {  
    int aMatrix[] = { 1, 4, 2, 5, 3, 6 };  
    int bMatrix[] = { 7, 8, 9, 10, 11, 12 };  
    int productMatrix[] = { 0, 0, 0, 0, 0, 0, 0, 0, 0 };  
 
    array_view<int, 2> a(3, 2, aMatrix);

    array_view<int, 2> b(2, 3, bMatrix);

    array_view<int, 2> product(3, 3, productMatrix);

    parallel_for_each(product.extent,  
        [=] (index<2> idx) restrict(amp) {  
            int row = idx[0];  
            int col = idx[1];  
            for (int inner = 0; inner <2; inner++) {  
                product[idx] += a(row, inner)* b(inner, col);  
            }  
        });  
 
    product.synchronize();
 
    for (int row = 0; row <3; row++) {  
        for (int col = 0; col <3; col++) { 
            //std::cout << productMatrix[row*3 + col] << "  ";  
            std::cout << product(row, col) << "  ";  
        }    
        std::cout << "\n";  
    }  
}  
```  
  
    The AMP code resembles the non-AMP code. The call to `parallel_for_each` starts one thread for each element in `product.extent`, and replaces the `for` loops for row and column. The value of the cell at the row and column is available in `idx`. You can access the elements of an `array_view` object by using either the `[]` operator and an index variable, or the `()` operator and the row and column variables. The example demonstrates both methods. The `array_view::synchronize` method copies the values of the `product` variable back to the `productMatrix` variable.  
  
2. Добавьте следующий `include` и `using` инструкций в верхней части MatrixMultiply.cpp.  
  
```cpp  
#include <amp.h>  
using namespace concurrency;  
```  
  
3. Изменить `main` метод для вызова `MultiplyWithAMP` метод.  
  
```cpp  
void main() {  
    MultiplyWithOutAMP();  
    MultiplyWithAMP();  
    getchar();  
}  
```  
  
4. Выберите **Ctrl**+**F5** сочетания клавиш, чтобы начать отладку и проверьте, правильно ли выходные данные.  
  
5. Выберите **пробел** выход из приложения.  
  
## <a name="multiplication-with-tiling"></a>Умножение с мозаичное заполнение  
 
Мозаичное заполнение — это метод, в котором секционировать данные на подмножества одинакового размера, которые известны как плитки. При использовании мозаичного заполнения, изменить три вещи.  
  
- Можно создать `tile_static` переменные. Доступ к данным в `tile_static` пространство может быть много раз быстрее, чем доступ к данным в глобальной области. Экземпляр `tile_static` переменная создается для каждого элемента мозаики, и все потоки в мозаике имеют доступ к этой переменной. Основное преимущество мозаичного замощения — выигрыш в производительности из-за `tile_static` доступа.  
  
- Можно вызвать [tile_barrier::wait](reference/tile-barrier-class.md#wait) метода все потоки в одну плитку в указанной строке кода. Не гарантирует порядок, в котором будут выполняться потоки, только что все потоки в одну плитку останавливается на вызове `tile_barrier::wait` продолжения выполнения.  

- У вас есть доступ к индексу потока по отношению к всего `array_view` объекта и индексу относительно плитки. С помощью локального индекса, может сделать ваш код проще читать и отлаживать.  
  
Чтобы воспользоваться преимуществами мозаичного заполнения в Перемножение матриц, необходимо разделить матрицы плитки алгоритм, а затем скопировать данные плиток в `tile_static` переменные для более быстрого доступа. В этом примере матрицы разделена на submatrices одинакового размера. Продукт находится путем умножения submatrices. Две матрицы и продуктов в этом примере являются:  
  
![4&#45;по&#45;4 матрицы](../../parallel/amp/media/campmatrixatiled.png "campmatrixatiled")  
  
![4&#45;по&#45;4 матрицы](../../parallel/amp/media/campmatrixbtiled.png "campmatrixbtiled")  
  
![4&#45;по&#45;4 матрицы](../../parallel/amp/media/campmatrixproducttiled.png "campmatrixproducttiled")  
  
Матрицы секционируются в матрицах четыре 2 x 2, которые определяются следующим образом:  
  
![4&#45;по&#45;4 матрицы, секционирована на 2&#45;по&#45;2 sub&#45;матрицы](../../parallel/amp/media/campmatrixapartitioned.png "campmatrixapartitioned")  
  
![4&#45;по&#45;4 матрицы, секционирована на 2&#45;по&#45;2 sub&#45;матрицы](../../parallel/amp/media/campmatrixbpartitioned.png "campmatrixbpartitioned")  
  
Произведение A и B теперь могут быть записаны и вычисляется следующим образом:  
  
![4&#45;по&#45;4 матрицы, секционирована на 2&#45;по&#45;2 sub&#45;матрицы](../../parallel/amp/media/campmatrixproductpartitioned.png "campmatrixproductpartitioned")  
  
Так как матрицы `a` через `h` матрицы 2 x 2, все продукты и суммы значений их также матрицы 2 x 2. Также следует, что A * B является матрицу 4 x 4 должным образом. Чтобы быстро проверить алгоритм, вычисления значения параметра элемент в первой строке и первом столбце в продукте. В примере, который будет иметь значение элемента в первой строке и первом столбце `ae + bg`. Вам только нужно рассчитать первый столбец, первая строка `ae` и `bg` каждого термина. Это значение для `ae` является `1*1 + 2*5 = 11`. Значение для `bg` является `3*1 + 4*5 = 23`. Конечное значение будет `11 + 23 = 34`, которое является верным.  
  
Для реализации этого алгоритма, код:  
  
- Использует `tiled_extent` вместо объекта `extent` объекта в `parallel_for_each` вызова.  
  
- Использует `tiled_index` вместо объекта `index` объекта в `parallel_for_each` вызова.  
  
- Создает `tile_static` переменные для хранения submatrices.  
  
- Использует `tile_barrier::wait` метод потоков для расчета продуктов submatrices.  
  
### <a name="to-multiply-by-using-amp-and-tiling"></a>Умножение с помощью AMP и мозаичного заполнения  
  
1. В MatrixMultiply.cpp, добавьте следующий код перед `main` метод.  
  
```cpp  
void MultiplyWithTiling() {  
    // The tile size is 2.  
    static const int TS = 2;  

    // The raw data.  
    int aMatrix[] = { 1, 2, 3, 4, 5, 6, 7, 8, 1, 2, 3, 4, 5, 6, 7, 8 };  
    int bMatrix[] = { 1, 2, 3, 4, 5, 6, 7, 8, 1, 2, 3, 4, 5, 6, 7, 8 };  
    int productMatrix[] = { 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0 };  

    // Create the array_view objects.  
    array_view<int, 2> a(4, 4, aMatrix);  
    array_view<int, 2> b(4, 4, bMatrix);  
    array_view<int, 2> product(4, 4, productMatrix);  
  
    // Call parallel_for_each by using 2x2 tiles.  
    parallel_for_each(product.extent.tile<TS, TS>(),  
        [=] (tiled_index<TS, TS> t_idx) restrict(amp)   
        { 
            // Get the location of the thread relative to the tile (row, col) 
            // and the entire array_view (rowGlobal, colGlobal).  
            int row = t_idx.local[0];   
            int col = t_idx.local[1];  
            int rowGlobal = t_idx.global[0];  
            int colGlobal = t_idx.global[1];  
            int sum = 0;  
  
            // Given a 4x4 matrix and a 2x2 tile size, this loop executes twice for each thread.  
            // For the first tile and the first loop, it copies a into locA and e into locB.  
            // For the first tile and the second loop, it copies b into locA and g into locB.  
            for (int i = 0; i < 4; i += TS) {  
                tile_static int locA[TS][TS];  
                tile_static int locB[TS][TS];  
                locA[row][col] = a(rowGlobal, col + i);  
                locB[row][col] = b(row + i, colGlobal);  
                // The threads in the tile all wait here until locA and locB are filled.  
                t_idx.barrier.wait();  

                // Return the product for the thread. The sum is retained across 
                // both iterations of the loop, in effect adding the two products 
                // together, for example, a*e.  
                for (int k = 0; k < TS; k++) {  
                    sum += locA[row][k] * locB[k][col];  
                }  

                // All threads must wait until the sums are calculated. If any threads  
                // moved ahead, the values in locA and locB would change.        
                t_idx.barrier.wait();
                // Now go on to the next iteration of the loop.            
            }  
            
            // After both iterations of the loop, copy the sum to the product variable by using the global location.  
            product[t_idx.global] = sum;  
        });

    // Copy the contents of product back to the productMatrix variable.  
    product.synchronize();
 
    for (int row = 0; row <4; row++) {  
        for (int col = 0; col <4; col++) { 
            // The results are available from both the product and productMatrix variables. 
            //std::cout << productMatrix[row*3 + col] << "  ";  
            std::cout << product(row, col) << "  ";  
        }  
        std::cout << "\n";  
    }  
}  
```  
  
    This example is significantly different than the example without tiling. The code uses these conceptual steps:  
  
    1. Копировать элементы плитки [0,0] `a` в `locA`. Копировать элементы плитки [0,0] `b` в `locB`. Обратите внимание, что `product` выполняется мозаичное заполнение, не `a` и `b`. Таким образом, использовать глобальный индексы для доступа к `a, b`, и `product`. Вызов `tile_barrier::wait` важно. Останавливает все потоки в плитке до оба `locA` и `locB` заполняются.  
  
    2. Умножьте `locA` и `locB` и помещать результаты в `product`.  
  
    3. Копировать элементы плитки [0,1] `a` в `locA`. Копировать элементы плитки [1,0] `b` в `locB`.  
  
    4. Умножьте `locA` и `locB` и добавить их к результатам, которые уже `product`.  
  
    5. Умножение плитки [0,0] завершена.  
  
    6. Повторите для других трех плиток. Имеется индексирование не специально для плитки, а потоки могут выполняться в любом порядке. Так как каждый поток выполняется, `tile_static` переменные создаются для каждой плитки соответствующим образом и вызов `tile_barrier::wait` управляет выполнением программы.  
  
    7. Внимательно просмотреть алгоритм, обратите внимание, что каждый submatrix загружается в `tile_static` памяти дважды. Эта передача данных времени. Тем не менее когда данные находятся в `tile_static` памяти, доступ к данным осуществляется гораздо быстрее. Поскольку вычисление продуктов требует повторного доступа к значениям в submatrices, является увеличение общей производительности. Для каждого алгоритма службы "Экспериментирование" необходим для поиска оптимального алгоритма и размер плитки.  
  
         В примерах не AMP и не плитки, каждый элемент A и B выполняется четыре раза из глобальной памяти, для которого требуется вычислить продукта. В примере плитки, каждому элементу осуществляется дважды из глобальной памяти и четыре раза `tile_static` памяти. Это не прирост производительности. Тем не менее если A и B были 1024 x 1024 матрицы и размер мозаики были 16, отсутствует прирост производительности. В этом случае каждый элемент будет необходимо скопировать в `tile_static` памяти только 16 раз доступ к ним из `tile_static` памяти раз на 1024.  
  
2. Измените основной метод для вызова `MultiplyWithTiling` метод, как показано.  
  
```cpp  
void main() {  
    MultiplyWithOutAMP();  
    MultiplyWithAMP();  
    MultiplyWithTiling();  
    getchar();  
}  
```  
  
3. Выберите **Ctrl**+**F5** сочетания клавиш, чтобы начать отладку и проверьте, правильно ли выходные данные.  
  
4. Выберите **пространства** панели, чтобы выйти из приложения.  
  
## <a name="see-also"></a>См. также  
 
[C++ AMP (C++ Accelerated Massive Parallelism)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)   
[Пошаговое руководство. Отладка приложения C++ AMP](../../parallel/amp/walkthrough-debugging-a-cpp-amp-application.md)