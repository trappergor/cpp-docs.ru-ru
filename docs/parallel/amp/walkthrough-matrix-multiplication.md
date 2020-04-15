---
title: Пошаговое руководство. Умножение матриц
ms.date: 04/23/2019
ms.assetid: 61172e8b-da71-4200-a462-ff3a908ab0cf
ms.openlocfilehash: f30f8dc235bf0e76c342bea26a35bcbb36cfa237
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366801"
---
# <a name="walkthrough-matrix-multiplication"></a>Пошаговое руководство. Умножение матриц

Это поэтапное пошаговоц-пошаговоц-пошаговоц демонстрирует, как использовать АМП для ускорения выполнения умножения матрицы. Представлены два алгоритма: один без плитки и один с плиткой.

## <a name="prerequisites"></a>Предварительные требования

Перед началом:

- Прочитайте [обзор АМП СЗА](../../parallel/amp/cpp-amp-overview.md).

- Читать [С помощью плитки](../../parallel/amp/using-tiles.md).

- Убедитесь, что вы работаете по крайней мере Windows 7, или Windows Server 2008 R2.

### <a name="to-create-the-project"></a>Создание проекта

Инструкции по созданию нового проекта варьируются в зависимости от того, какую версию Visual Studio вы установили. Чтобы просмотреть документацию для предпочтительной версии Visual Studio, используйте элемент управления селектора **версии.** Он находится в верхней части таблицы содержимого на этой странице.

::: moniker range="vs-2019"

### <a name="to-create-the-project-in-visual-studio-2019"></a>Создать проект в Visual Studio 2019

1. В строке меню выберите **Файл** > **Создать** > **Проект**, чтобы открыть диалоговое окно **Создание проекта**.

1. В верхней части диалогового окна для параметра **Язык** выберите значение **C++**, для параметра **Платформа** — значение **Windows**, а для параметра **Тип проекта** — значение **Консоль**.

1. Из отфильтрованного списка типов проектов выберите **Пустой проект,** а затем выберите **Next**. На следующей странице введите *MatrixMultiply* в поле **имен,** чтобы указать имя проекта, и укажите местоположение проекта при желании.

   ![Новое приложение для консолей](../../build/media/mathclient-project-name-2019.png "Новое приложение для консолей")

1. Нажмите кнопку **Создать**, чтобы создать клиентский проект.

1. В **Solution Explorer**откройте меню ярлыка для **исходных файлов,** а затем выберите **Добавить** > **новый элемент.**

1. В диалоговом поле **Добавить новый элемент** выберите **файл C's (.cpp),** введите *MatrixMultiply.cpp* в поле **Name,** а затем выберите кнопку **Добавить.**

::: moniker-end

::: moniker range="<=vs-2017"

### <a name="to-create-a-project-in-visual-studio-2017-or-2015"></a>Создание проекта в Visual Studio 2017 или 2015

1. В меню-баре в Visual Studio выберите **File** > **New** > **Project.**

1. Под **установленным** в шаблонах панели, выберите **Visual C .**

1. Выберите **Пустой проект,** введите *MatrixMultiply* в поле **имени,** а затем выберите кнопку **OK.**

1. Нажмите кнопку **Далее**.

1. В **Solution Explorer**откройте меню ярлыка для **исходных файлов,** а затем выберите **Добавить** > **новый элемент.**

1. В диалоговом поле **Добавить новый элемент** выберите **файл C's (.cpp),** введите *MatrixMultiply.cpp* в поле **Name,** а затем выберите кнопку **Добавить.**

::: moniker-end

## <a name="multiplication-without-tiling"></a>Умножение без плитки

В этом разделе рассмотрим умножение двух матриц, A и B, которые определяются следующим образом:

![3&#45;по&#45;2 матрицы А](../../parallel/amp/media/campmatrixanontiled.png "3&#45;по&#45;2 матрицы А")

![2&#45;по&#45;3 матрицы B](../../parallel/amp/media/campmatrixbnontiled.png "2&#45;по&#45;3 матрицы B")

A - это матрица 3 на 2, а B - матрица 2 на 3. Продуктом умножения A на B является следующая матрица 3 на 3. Продукт рассчитывается путем умножения строк A по столбцов элемента B по элементам.

![3&#45;по&#45;3 матрицы продукта](../../parallel/amp/media/campmatrixproductnontiled.png "3&#45;по&#45;3 матрицы продукта")

### <a name="to-multiply-without-using-c-amp"></a>Умножать без использования СЗ АМП

1. Откройте MatrixMultiply.cpp и используйте следующий код для замены существующего кода.

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

   int main() {
       MultiplyWithOutAMP();
       getchar();
   }
   ```

   Алгоритм представляет собой простую реализацию определения матричного умножения. Он не использует никаких параллельных или потоковых алгоритмов для сокращения времени вычисления.

1. В баре меню выберите **Файл** > **Сохранить все**.

1. Выберите ярлык клавиатуры **F5,** чтобы начать отладку и убедиться, что выход правильный.

1. Выберите **Enter** для выхода из приложения.

### <a name="to-multiply-by-using-c-amp"></a>Умножить с помощью СЗ АМП

1. В MatrixMultiply.cpp добавьте следующий `main` код перед методом.

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

   Код AMP напоминает код, не связанный с AMP. Вызов запускает `parallel_for_each` один поток для `product.extent`каждого элемента `for` в, и заменяет петли для строки и столбца. Значение ячейки в строке и столбце доступно в `idx`. Вы можете получить доступ `array_view` к элементам `[]` объекта, используя либо оператора `()` и переменную индекса, либо переменные оператора, строки и столбца. Пример демонстрирует оба метода. Метод `array_view::synchronize` копирует значения `product` переменной обратно к `productMatrix` переменной.

1. Добавьте `include` следующие и `using` заявления в верхней части MatrixMultiply.cpp.

   ```cpp
   #include <amp.h>
   using namespace concurrency;
   ```

1. Измените `main` метод вызова `MultiplyWithAMP` метода.

   ```cpp
   int main() {
       MultiplyWithOutAMP();
       MultiplyWithAMP();
       getchar();
   }
   ```

1. Нажмите на ярлык клавиатуры **Ctrl**+**F5,** чтобы начать отладку и убедиться, что выход правильный.

1. Нажмите на **Spacebar,** чтобы выйти из приложения.

## <a name="multiplication-with-tiling"></a>Умножение с помощью плитки

Tiling — это метод, при котором данные раздела на подмножества равных размеров, которые известны как плитки. Три вещи меняются при использовании плитки.

- Можно создавать `tile_static` переменные. Доступ к `tile_static` данным в космосе может быть во много раз быстрее, чем доступ к данным в глобальном пространстве. Для каждой `tile_static` плитки создается экземпляр переменной, и все потоки в плитке имеют доступ к переменной. Основным преимуществом плитки является повышение `tile_static` производительности благодаря доступу.

- Вы можете вызвать [tile_barrier::метод ожидания,](reference/tile-barrier-class.md#wait) чтобы остановить все потоки в одной плитке в заданной строке кода. Вы не можете гарантировать заказ, в который будут работать потоки, только то, что `tile_barrier::wait` все потоки в одной плитке остановятся при вызове до их продолжения выполнения.

- У вас есть доступ к индексу `array_view` потока относительно всего объекта и индексу относительно плитки. Используя локальный индекс, можно упростить чтение и отладку кода.

Чтобы воспользоваться преимуществами обработки в матричной умножении, алгоритм должен разделить матрицу `tile_static` на плитки, а затем скопировать данные плитки в переменные для более быстрого доступа. В этом примере матрица разделена на субматии одинакового размера. Продукт обнаруживается путем умножения субматрисов. Две матрицы и их продукт в этом примере:

![4&#45;по&#45;4 матрицы А](../../parallel/amp/media/campmatrixatiled.png "4&#45;по&#45;4 матрицы А")

![4&#45;по&#45;4 матрицы B](../../parallel/amp/media/campmatrixbtiled.png "4&#45;по&#45;4 матрицы B")

![4&#45;по матрице&#45;4 продукта](../../parallel/amp/media/campmatrixproducttiled.png "4&#45;по матрице&#45;4 продукта")

Матрицы разделены на четыре матрицы 2x2, которые определяются следующим образом:

![4&#45;по&#45;4 матрицы A разделены на 2&#45;&#45;2 под&#45;матрицы](../../parallel/amp/media/campmatrixapartitioned.png "4&#45;по&#45;4 матрицы A разделены на 2&#45;&#45;2 под&#45;матрицы")

![4&#45;&#45;4 матрицы B, разделенной на 2&#45;на 2&#45;под&#45;матрицы](../../parallel/amp/media/campmatrixbpartitioned.png "4&#45;&#45;4 матрицы B, разделенной на 2&#45;на 2&#45;под&#45;матрицы")

Продукт A и B теперь может быть написан и рассчитан следующим образом:

![4&#45;по&#45;4 матрицы A B разделены на 2&#45;&#45;2 под&#45;матрицы](../../parallel/amp/media/campmatrixproductpartitioned.png "4&#45;по&#45;4 матрицы A B разделены на 2&#45;&#45;2 под&#45;матрицы")

Потому что `a` `h` матрицы через 2x2 матрицы, все продукты и суммы из них также 2x2 матрицы. Из этого также следует, что продукт A и B является матрицей 4x4, как и ожидалось. Чтобы быстро проверить алгоритм, вычислите значение элемента в первом ряду, первого столбца в продукте. В примере это будет значение элемента в первом ряду `ae + bg`и первом столбце . Вам нужно вычислить только первый столбец, первый `ae` ряд и `bg` для каждого термина. Это значение `ae` `(1 * 1) + (2 * 5) = 11`для . Значение `bg` равно `(3 * 1) + (4 * 5) = 23`. Окончательное `11 + 23 = 34`значение, которое является правильным.

Для реализации этого алгоритма код:

- Использует `tiled_extent` объект вместо `extent` объекта в `parallel_for_each` вызове.

- Использует `tiled_index` объект вместо `index` объекта в `parallel_for_each` вызове.

- Создает `tile_static` переменные для хранения субматрисов.

- Использует `tile_barrier::wait` метод, чтобы остановить потоки для расчета продуктов субматрисов.

### <a name="to-multiply-by-using-amp-and-tiling"></a>Умножить с помощью AMP и плитки

1. В MatrixMultiply.cpp добавьте следующий `main` код перед методом.

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

   Этот пример значительно отличается от примера без плитки. Код использует следующие концептуальные шаги:
   1. Копировать элементы плитки в `a` . `locA` Копировать элементы плитки в `b` . `locB` Обратите `product` внимание, что `a` плитка, нет и `b`. Таким образом, вы используете `a, b`глобальные `product`индексы для доступа, и . Призыв к `tile_barrier::wait` имеет важное значение. Он останавливает все нити в плитке до тех пор, пока оба `locA` и `locB` заполнены.

   1. Умножьте `locA` и `locB` `product`и поставьте результаты в .

   1. Копировать элементы плитки 0,1 `a` `locA`"в . Копировать элементы плитки в `b` . `locB`

   1. Умножьте `locA` и `locB` и добавьте `product`их к результатам, которые уже находятся в .

   1. Умножение плитки завершено.

   1. Повторите для других четырех плиток. Нет индексации специально для плиток, и потоки могут выполняться в любом порядке. При выполнении каждого `tile_static` потока для каждой плитки создаются `tile_barrier::wait` переменные, а для управления потоком программы — вызов.

   1. При внимательном изучении алгоритма обратите внимание, что `tile_static` каждая подматрицка загружается в память дважды. Эта передача данных требует времени. Однако, как только `tile_static` данные в памяти, доступ к данным гораздо быстрее. Поскольку для расчета продуктов требуется повторный доступ к значениям в субматидах, наблюдается общий прирост производительности. Для каждого алгоритма требуется эксперимент, чтобы найти оптимальный алгоритм и размер плитки.

   В примерах, не относясь к AMP и не являнию плитки, каждый элемент A и B доступен четыре раза из глобальной памяти для расчета продукта. В примере плитки каждый элемент получает доступ дважды `tile_static` из глобальной памяти и четыре раза из памяти. Это не является значительным повышением производительности. Однако, если бы Матрицы A и B были 1024x1024, а размер плитки — 16, то было бы значительное увеличение производительности. В этом случае каждый элемент `tile_static` будет скопирован в память `tile_static` только 16 раз и доступ из памяти 1024 раза.

1. Измените основной метод `MultiplyWithTiling` вызова метода, как показано на рисунке.

   ```cpp
   int main() {
       MultiplyWithOutAMP();
       MultiplyWithAMP();
       MultiplyWithTiling();
       getchar();
   }
   ```

1. Нажмите на ярлык клавиатуры **Ctrl**+**F5,** чтобы начать отладку и убедиться, что выход правильный.

1. Нажмите на **пробел,** чтобы выйти из приложения.

## <a name="see-also"></a>См. также раздел

[C++ AMP (C++ Accelerated Massive Parallelism)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)<br/>
[Пошаговое руководство. Отладка приложения C++ AMP](../../parallel/amp/walkthrough-debugging-a-cpp-amp-application.md)
