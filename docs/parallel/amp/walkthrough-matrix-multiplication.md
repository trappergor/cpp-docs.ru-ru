---
title: Пошаговое руководство. Умножение матриц
ms.date: 04/23/2019
ms.assetid: 61172e8b-da71-4200-a462-ff3a908ab0cf
ms.openlocfilehash: afa9dba8938f9d701b8f21ca3575eb06eb688ac0
ms.sourcegitcommit: 18d3b1e9cdb4fc3a76f7a650c31994bdbd2bde64
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/29/2019
ms.locfileid: "64877486"
---
# <a name="walkthrough-matrix-multiplication"></a>Пошаговое руководство. Умножение матриц

Это пошаговое руководство демонстрирует использование C++ AMP для ускорения выполнения Перемножение матриц. Появится два алгоритма и один без заполнения с мозаичное заполнение.

## <a name="prerequisites"></a>Предварительные требования

Перед началом работы

- Чтение [Обзор C++ AMP](../../parallel/amp/cpp-amp-overview.md).

- Чтение [с помощью плитки](../../parallel/amp/using-tiles.md).

- Убедитесь, что вы используете по крайней мере Windows 7 или Windows Server 2008 R2.

### <a name="to-create-the-project"></a>Создание проекта

Инструкции по созданию нового проекта зависит от установленной версии Visual Studio. Убедитесь, что у вас есть выбора версий в верхнем левом углу задайте правильную версию.

::: moniker range="vs-2019"

### <a name="to-create-the-project-in-visual-studio-2019"></a>Чтобы создать проект в Visual Studio 2019 г.

1. В строке меню выберите **файл** > **New** > **проекта** открыть **создайте новый проект** диалоговое окно.

1. В верхней части диалогового окна, задайте **языка** для **C++**, задайте **платформы** для **Windows**и задайте **типпроекта** для **консоли**. 

1. В отфильтрованном списке типов проектов выберите **пустой проект** выберите **Далее**. На следующей странице введите *MatrixMultiply* в **имя** поле для указания имени проекта и указать расположение проекта, при необходимости.

   ![Консольное приложение](../../build/media/mathclient-project-name-2019.png "консольное приложение")

1. Выберите **создать** кнопку, чтобы создать клиентский проект.

1. В **обозревателе решений**, откройте контекстное меню для **исходные файлы**, а затем выберите **добавить** > **новый элемент**.

1. В **Добавление нового элемента** выберите **файл C++ (.cpp)**, введите *MatrixMultiply.cpp* в **имя** поле, а затем выберите  **Добавление** кнопки.

::: moniker-end

::: moniker range="<=vs-2017"

### <a name="to-create-a-project-in-visual-studio-2017-or-2015"></a>Создание проекта в Visual Studio 2017 или 2015

1. В строке меню в Visual Studio, выберите **файл** > **New** > **проекта**.

1. В разделе **установленные** в области «Шаблоны» выберите **Visual C++**.

1. Выберите **пустой проект**, введите *MatrixMultiply* в **имя** поле, а затем выберите **ОК** кнопки.

1. Нажмите кнопку **Далее**.

1. В **обозревателе решений**, откройте контекстное меню для **исходные файлы**, а затем выберите **добавить** > **новый элемент**.

1. В **Добавление нового элемента** выберите **файл C++ (.cpp)**, введите *MatrixMultiply.cpp* в **имя** поле, а затем выберите  **Добавление** кнопки.

::: moniker-end

## <a name="multiplication-without-tiling"></a>Умножение без заполнения

В этом разделе описано рассмотрим умножения двух матриц, А и Б, которые определяются следующим образом:

![3&#45;по&#45;2 матрицы A](../../parallel/amp/media/campmatrixanontiled.png "3&#45;по&#45;2 матрицы A")

![2&#45;по&#45;3 матрицы B](../../parallel/amp/media/campmatrixbnontiled.png "2&#45;по&#45;матрицы 3 B")

Объект является матрицу 3 x 2, а B — матрица 2 x 3. Результат умножения A, B является следующая матрица 3 x 3. Продукт вычисляется путем умножения строки типа по столбцам B поэлементно.

![3&#45;по&#45;матрицы 3 продукта](../../parallel/amp/media/campmatrixproductnontiled.png "3&#45;по&#45;матрицы 3 продукта")

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

   Алгоритм представляет собой простую реализацию, определения Перемножение матриц. Он не использует любые алгоритмы параллельных или потоками для уменьшения времени вычислений.

1. В строке меню выберите **Файл** > **Сохранить все**.

1. Выберите **F5** сочетания клавиш, чтобы начать отладку и проверьте, правильно ли выходные данные.

1. Выберите **ввод** выход из приложения.

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

   AMP код напоминает код, не AMP. Вызов `parallel_for_each` запускает один поток для каждого элемента в `product.extent`и заменяет `for` циклы для строк и столбцов. Значение ячейки в строке и столбце доступен в `idx`. Можно получить доступ к элементы `array_view` объекта, либо при помощи `[]` оператор и переменная индекса, или `()` оператор и переменных строк и столбцов. В этом примере оба метода. `array_view::synchronize` Метод копирует значения `product` переменной обратно `productMatrix` переменной.

1. Добавьте следующий `include` и `using` инструкций в верхней части MatrixMultiply.cpp.

   ```cpp
   #include <amp.h>
   using namespace concurrency;
   ```

1. Изменить `main` метод для вызова `MultiplyWithAMP` метод.

   ```cpp
   void main() {
       MultiplyWithOutAMP();
       MultiplyWithAMP();
       getchar();
   }
   ```

1. Нажмите клавишу **Ctrl**+**F5** сочетания клавиш, чтобы начать отладку и проверьте, правильно ли выходные данные.

1. Нажмите клавишу **пробел** выход из приложения.

## <a name="multiplication-with-tiling"></a>Умножение с мозаичное заполнение

Мозаичное заполнение — это метод, в котором секционировать данные на подмножества одинакового размера, которые известны как плитки. При использовании мозаичного заполнения, изменить три вещи.

- Можно создать `tile_static` переменные. Доступ к данным в `tile_static` пространство может быть много раз быстрее, чем доступ к данным в глобальной области. Экземпляр `tile_static` переменная создается для каждого элемента мозаики, и все потоки в мозаике имеют доступ к этой переменной. Основное преимущество мозаичного замощения — выигрыш в производительности из-за `tile_static` доступа.

- Можно вызвать [tile_barrier::wait](reference/tile-barrier-class.md#wait) метода все потоки в одну плитку в указанной строке кода. Не гарантирует порядок, в котором будут выполняться потоки, только что все потоки в одну плитку останавливается на вызове `tile_barrier::wait` продолжения выполнения.

- У вас есть доступ к индексу потока по отношению к всего `array_view` объекта и индексу относительно плитки. С помощью локального индекса, может сделать ваш код проще читать и отлаживать.

Чтобы воспользоваться преимуществами мозаичного заполнения в Перемножение матриц, необходимо разделить матрицы плитки алгоритм, а затем скопировать данные плиток в `tile_static` переменные для более быстрого доступа. В этом примере матрицы разделена на submatrices одинакового размера. Продукт находится путем умножения submatrices. Две матрицы и продуктов в этом примере являются:

![4&#45;по&#45;4 матрицы A](../../parallel/amp/media/campmatrixatiled.png "4&#45;по&#45;4 матрицы A")

![4&#45;по&#45;4 матрицы B](../../parallel/amp/media/campmatrixbtiled.png "4&#45;по&#45;4 матрицы B")

![4&#45;по&#45;матрицу 4 продукта](../../parallel/amp/media/campmatrixproducttiled.png "4&#45;по&#45;матрицу 4 продукта")

Матрицы секционируются в матрицах четыре 2 x 2, которые определяются следующим образом:

![4&#45;по&#45;4 матрицы A, секционирована на 2&#45;по&#45;2 sub&#45;матрицы](../../parallel/amp/media/campmatrixapartitioned.png "4&#45;по&#45;4 матрицы A, секционирована на 2&#45;по&#45;2 sub&#45;матрицы")

![4&#45;по&#45;4 матрицы B разделена 2&#45;по&#45;2 sub&#45;матрицы](../../parallel/amp/media/campmatrixbpartitioned.png "4&#45;по&#45;4 матрицы B разделена 2&#45;по&#45;2 sub&#45;матрицы")

Произведение A и B теперь могут быть записаны и вычисляется следующим образом:

![4&#45;по&#45;4 матрицы B, секционирована на 2&#45;по&#45;2 sub&#45;матрицы](../../parallel/amp/media/campmatrixproductpartitioned.png "4&#45;по&#45;4 матрицы B, секционирована на 2&#45;по&#45;2 sub&#45;матрицы")

Так как матрицы `a` через `h` матрицы 2 x 2, все продукты и суммы значений их также матрицы 2 x 2. Также следует, что продукт A и B является матрицу 4 x 4 должным образом. Чтобы быстро проверить алгоритм, вычисления значения параметра элемент в первой строке и первом столбце в продукте. В примере, который будет иметь значение элемента в первой строке и первом столбце `ae + bg`. Вам только нужно рассчитать первый столбец, первая строка `ae` и `bg` каждого термина. Это значение для `ae` является `(1 * 1) + (2 * 5) = 11`. Значение для `bg` является `(3 * 1) + (4 * 5) = 23`. Конечное значение будет `11 + 23 = 34`, которое является верным.

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

   В этом примере значительно отличается от примера без заполнения. В коде используются следующие основные действия:
   1. Копировать элементы плитки [0,0] `a` в `locA`. Копировать элементы плитки [0,0] `b` в `locB`. Обратите внимание, что `product` выполняется мозаичное заполнение, не `a` и `b`. Таким образом, использовать глобальный индексы для доступа к `a, b`, и `product`. Вызов `tile_barrier::wait` важно. Останавливает все потоки в плитке до оба `locA` и `locB` заполняются.

   1. Умножьте `locA` и `locB` и помещать результаты в `product`.

   1. Копировать элементы плитки [0,1] `a` в `locA`. Копировать элементы плитки [1,0] `b` в `locB`.

   1. Умножьте `locA` и `locB` и добавить их к результатам, которые уже `product`.

   1. Умножение плитки [0,0] завершена.

   1. Повторите для других трех плиток. Имеется индексирование не специально для плитки, а потоки могут выполняться в любом порядке. Так как каждый поток выполняется, `tile_static` переменные создаются для каждой плитки соответствующим образом и вызов `tile_barrier::wait` управляет выполнением программы.

   1. Внимательно просмотреть алгоритм, обратите внимание, что каждый submatrix загружается в `tile_static` памяти дважды. Эта передача данных времени. Тем не менее когда данные находятся в `tile_static` памяти, доступ к данным осуществляется гораздо быстрее. Поскольку вычисление продуктов требует повторного доступа к значениям в submatrices, является увеличение общей производительности. Для каждого алгоритма службы "Экспериментирование" необходим для поиска оптимального алгоритма и размер плитки.

   В примерах не AMP и не плитки, каждый элемент A и B выполняется четыре раза из глобальной памяти, для которого требуется вычислить продукта. В примере плитки, каждому элементу осуществляется дважды из глобальной памяти и четыре раза `tile_static` памяти. Это не прирост производительности. Тем не менее если A и B были 1024 x 1024 матрицы и размер мозаики были 16, отсутствует прирост производительности. В этом случае каждый элемент будет необходимо скопировать в `tile_static` памяти только 16 раз доступ к ним из `tile_static` памяти раз на 1024.

1. Измените основной метод для вызова `MultiplyWithTiling` метод, как показано.

   ```cpp
   void main() {
       MultiplyWithOutAMP();
       MultiplyWithAMP();
       MultiplyWithTiling();
       getchar();
   }
   ```

1. Нажмите клавишу **Ctrl**+**F5** сочетания клавиш, чтобы начать отладку и проверьте, правильно ли выходные данные.

1. Нажмите клавишу **пространства** панели, чтобы выйти из приложения.

## <a name="see-also"></a>См. также

[C++ AMP (C++ Accelerated Massive Parallelism)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)<br/>
[Пошаговое руководство: отладка приложения C++ AMP](../../parallel/amp/walkthrough-debugging-a-cpp-amp-application.md)
