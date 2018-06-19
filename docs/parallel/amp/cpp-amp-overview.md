---
title: Обзор C++ AMP | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- C++ Accelerated Massive Parallelism, requirements
- C++ Accelerated Massive Parallelism, architecture
- C++ AMP
- C++ Accelerated Massive Parallelism, overview
- C++ Accelerated Massive Parallelism
ms.assetid: 9e593b06-6e3c-43e9-8bae-6d89efdd39fc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f8de31ab9009a84c04e594837a0c4fbf30758fea
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33694632"
---
# <a name="c-amp-overview"></a>Общие сведения о C++ AMP
C++ Accelerated Massive Parallelism (C++ AMP) ускоряет выполнение кода C++, используя преимущества параллельными данными оборудования, например графическом процессоре (GPU) на выделенной видеокарте. С помощью C++ AMP, можно составить код алгоритмы многомерных данных, чтобы с помощью параллелизма на разнородного оборудования можно ускорить выполнение. Модель программирования C++ AMP включает многомерные массивы, индексирование, перенос памяти, мозаичное заполнение и библиотеку математических функций. Расширения языка C++ AMP можно использовать для управления как данные перемещаются из ЦП в GPU и обратно, так что можно улучшить производительность.  
  
## <a name="system-requirements"></a>Требования к системе  
  
- [!INCLUDE[win7](../../build/includes/win7_md.md)], [!INCLUDE[win8](../../build/reference/includes/win8_md.md)], [!INCLUDE[winsvr08_r2](../../parallel/amp/includes/winsvr08_r2_md.md)] или [!INCLUDE[winserver8](../../build/reference/includes/winserver8_md.md)]  
  
-   Функция уровень DirectX 11 11.0 или более поздней версии оборудования  
  
-   Для отладки в программном эмуляторе [!INCLUDE[win8](../../build/reference/includes/win8_md.md)] или [!INCLUDE[winserver8](../../build/reference/includes/winserver8_md.md)] является обязательным. Для отладки на оборудовании необходимо установить драйверы для видеокарты. Дополнительные сведения см. в разделе [отладка кода GPU](/visualstudio/debugger/debugging-gpu-code).  
  
## <a name="introduction"></a>Вступление  
 В следующих двух примерах показаны основные компоненты C++ AMP. Предположим, что для добавления соответствующих элементов двух одномерных массивов. Например, может потребоваться добавить `{1, 2, 3, 4, 5}` и `{6, 7, 8, 9, 10}` для получения `{7, 9, 11, 13, 15}`. Без использования C++ AMP, можно написать следующий код для суммирования и отображения результатов.  
  
```cpp  
#include <iostream>  
  
void StandardMethod() {  
  
    int aCPP[] = {1, 2, 3, 4, 5};  
    int bCPP[] = {6, 7, 8, 9, 10};  
    int sumCPP[5];  
  
    for (int idx = 0; idx < 5; idx++)  
    {  
        sumCPP[idx] = aCPP[idx] + bCPP[idx];  
    }  
  
    for (int idx = 0; idx < 5; idx++)  
    {  
        std::cout << sumCPP[idx] << "\n";  
    }  
}  
  
```  
  
 Ниже приведены важные части кода.  
  
-   Данные: Данные состоят из трех массивов. Все имеют те же ранг (один) и длина (5).  
  
-   Итерации: Первый `for` цикла предоставляет механизм для перебора элементов в массивах. В первом содержится код, который должен выполняться для вычисления суммы `for` блока.  
  
-   Индекс: `idx` переменная получает доступ к отдельным элементам массивов.  
  
 Использование C++ AMP, можно написать следующий код вместо него.  
  
```cpp  
#include <amp.h>  
#include <iostream>  
using namespace concurrency;  
  
const int size = 5;  
  
void CppAmpMethod() {  
    int aCPP[] = {1, 2, 3, 4, 5};  
    int bCPP[] = {6, 7, 8, 9, 10};  
    int sumCPP[size];  
  
    // Create C++ AMP objects.  
    array_view<const int, 1> a(size, aCPP);  
    array_view<const int, 1> b(size, bCPP);  
    array_view<int, 1> sum(size, sumCPP);  
    sum.discard_data();  
  
    parallel_for_each(   
        // Define the compute domain, which is the set of threads that are created.  
        sum.extent,   
        // Define the code to run on each thread on the accelerator.  
        [=](index<1> idx) restrict(amp) {  
            sum[idx] = a[idx] + b[idx];  
        }  
    );  
  
    // Print the results. The expected output is "7, 9, 11, 13, 15".  
    for (int i = 0; i < size; i++) {  
        std::cout << sum[i] << "\n";  
    }  
}  
```  
  
 Те же основные элементы присутствуют, но используются конструкции C++ AMP:  
  
-   Данные: Можно использовать массивы C++ для создания трех C++ AMP [array_view](../../parallel/amp/reference/array-view-class.md) объектов. Необходимо указать четыре значения для построения `array_view` объект: значения данных, ранг, тип элемента и длина `array_view` объекта в каждом измерении. Ранг и тип передаются как параметры типа. Данные и длину, передаются как параметры конструктора. В этом примере массив C++, который передается в конструктор одномерный массив. Ранг и длина используются для создания в прямоугольную форму данных в `array_view` объекта и данные значения используются для заполнения массива. Также включает библиотеку времени выполнения [класс array](../../parallel/amp/reference/array-class.md), содержит интерфейс, который напоминает `array_view` класса и рассматривается далее в этой статье.  
  
-   Итерации: [parallel_for_each функции (C++ AMP)](reference/concurrency-namespace-functions-amp.md#parallel_for_each) предоставляет механизм для перебора элементов данных, или *вычислений домена*. В этом примере определяется домене вычислений `sum.extent`. Содержится код, который должен выполняться в лямбда-выражение или *функция ядра*. `restrict(amp)` Указывает, что используется только подмножество языка C++, может ускорить C++ AMP.  
  
-   Индекс: [класс index](../../parallel/amp/reference/index-class.md) переменной, `idx`, объявлен с рангом 1 для сопоставления ранг `array_view` объекта. С помощью индекса, можно получить доступ к отдельным элементам `array_view` объектов.  
  
## <a name="shaping-and-indexing-data-index-and-extent"></a>Данные по формированию и индексирования: индекс и степень  
 Необходимо указать значения данных и объявить вида данных, перед выполнением кода ядра. Все данные определяется как массив (прямоугольный), и можно определить массив будет иметь любой ранг (число измерений). Данные могут быть любого размера, в каком-либо из измерений.  
  
### <a name="index-class"></a>Класс index  
 [Класс index](../../parallel/amp/reference/index-class.md) указывает расположение в `array` или `array_view` объекта, инкапсулируя смещение от начала координат в каждом измерении в один объект. При таком доступе расположение в массиве, можно передать `index` объекта на оператор индексирования `[]`, вместо списка индексов целое число со знаком. Можно обращаться к элементам в каждом измерении с помощью [оператор array:: operator()](reference/array-class.md#operator_call) или [оператор array_view:: operator()](reference/array-view-class.md#operator_call).  
  
 В следующем примере создается одномерный индекс, который задает третий элемент в одномерном массиве `array_view` объекта. Индекс используется для печати третьему элементу в `array_view` объекта. Выходные данные — 3.  
  
```cpp  
int aCPP[] = {1, 2, 3, 4, 5};  
array_view<int, 1> a(5, aCPP);

index<1> idx(2);

std::cout << a[idx] << "\n";    
// Output: 3  
```  
  
 В следующем примере создается двухмерный индекс, который указывает элемент, где строки = 1 и столбце = 2 в двухмерный `array_view` объекта. Первый параметр в `index` конструктор — это компонент строки, а второй параметр — это компонент столбца. Выходные данные — 6.  
  
```cpp  
int aCPP[] = {1, 2, 3, 4, 5, 6};  
array_view<int, 2> a(2, 3, aCPP);  
  
index<2> idx(1, 2);  
  
std::cout <<a[idx] << "\n";    
// Output: 6  
```  
  
 В следующем примере создается трехмерного индекс, который указывает элемент где глубина = 0, строка = 1, а столбец = 3 в трехмерный массив `array_view` объекта. Обратите внимание, что первый параметр — это компонент глубины, второй параметр — это компонент строки, третий параметр — это компонент столбца. Выходные данные — 8.  
  
```cpp  
int aCPP[] = {  
    1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12,   
    1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12};  
 
array_view<int, 3> a(2, 3, 4, aCPP);

// Specifies the element at 3, 1, 0.  
index<3> idx(0, 1, 3);

std::cout << a[idx] << "\n";  
// Output: 8  
```  
  
### <a name="extent-class"></a>Класс extent  
 [Класс extent](../../parallel/amp/reference/extent-class.md) задает длину данных в каждом измерении массива `array` или `array_view` объекта. Можно создать экстент и использовать его для создания `array` или `array_view` объекта. Вы также можете получить экстент существующего `array` или `array_view` объекта. В следующем примере выводится длина экстент в каждой размерности `array_view` объекта.  
  
```cpp  
int aCPP[] = {  
    1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12,   
    1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12};  
// There are 3 rows and 4 columns, and the depth is two.  
array_view<int, 3> a(2, 3, 4, aCPP);

std::cout << "The number of columns is " << a.extent[2] << "\n";  
std::cout << "The number of rows is " << a.extent[1] << "\n";  
std::cout << "The depth is " << a.extent[0] << "\n";  
std::cout << "Length in most significant dimension is " << a.extent[0] << "\n";  
```  
  
 В следующем примере создается `array_view` объект, который имеет те же измерения как объект в предыдущем примере, но в этом примере используется `extent` объекта вместо использования явных параметров в `array_view` конструктора.  
  
```cpp  
int aCPP[] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24};  
extent<3> e(2, 3, 4);

array_view<int, 3> a(e, aCPP);

std::cout << "The number of columns is " << a.extent[2] << "\n";  
std::cout << "The number of rows is " << a.extent[1] << "\n";  
std::cout << "The depth is " << a.extent[0] << "\n";  
```  
  
## <a name="moving-data-to-the-accelerator-array-and-arrayview"></a>Перемещение данных для сочетания клавиш: массив и array_view  
 В библиотеке времени выполнения определяются два контейнера данных, которые используются для перемещения данных для сочетания клавиш. Они являются [класс array](../../parallel/amp/reference/array-class.md) и [класс array_view](../../parallel/amp/reference/array-view-class.md). `array` Класса является класс контейнера, который создает глубокую копию данных, при создании объекта. `array_view` Класса является класс-оболочку, которая копирует данные, когда функция ядра обращается к данным. При необходимости на устройстве источника данных данные копируются обратно.  
  
### <a name="array-class"></a>Класс array  
 Если `array` объект создан, глубокую копию данных создается на сочетания клавиш, если вы используете конструктор, который включает указатель на набор данных. Функция ядра изменяет копией на сочетания клавиш. После завершения выполнения функции ядра необходимо скопировать данные в структуру источника данных. Этот пример умножает каждый элемент в векторе 10. После завершения работы функции ядра `vector conversion operator` используется для копирования данных обратно в объекте vector.  
  
```cpp  
std::vector<int> data(5);

for (int count = 0; count <5; count++)   
{  
    data[count] = count;  
}  
 
array<int, 1> a(5, data.begin(), data.end());
 
parallel_for_each(
    a.extent, 
    [=, &a](index<1> idx) restrict(amp) {  
        a[idx] = a[idx]* 10;  
    });
  
data = a;  
for (int i = 0; i < 5; i++)   
{  
    std::cout << data[i] << "\n";  
}  
```  
  
### <a name="arrayview-class"></a>Класс array_view  
 `array_view` Содержит практически те же члены, как `array` класс, но базовое поведение не совпадает. Данные, передаваемые `array_view` конструктор не реплицируются в GPU, как в случае `array` конструктор. Вместо этого данные копируются сочетаний клавиш при выполнении функции ядра. Таким образом Если создать два `array_view` объектов, использующих те же данные и `array_view` объекты ссылаются на одно и то же пространство памяти. При этом необходимо синхронизировать все многопоточного доступа. Главное преимущество использования `array_view` класс находится в том, что данные передаются только в том случае, если это необходимо.  
  
### <a name="comparison-of-array-and-arrayview"></a>Сравнение массивов и array_view  
 В следующей таблице показаны сходства и различия между `array` и `array_view` классы.  
  
|Описание|array - класс|array_view - класс|  
|-----------------|-----------------|-----------------------|  
|Если определяется ранг|Во время компиляции.|Во время компиляции.|  
|Если определить экстент|Во время выполнения.|Во время выполнения.|  
|Фигура|Прямоугольной.|Прямоугольной.|  
|Хранение данных|— Это контейнер данных.|Является оболочкой данных.|  
|Копировать|Явные и глубокую копию в определение.|Неявные копирования, если доступ осуществляется с помощью функции ядра.|  
|Извлечение данных|Путем копирования объекта в потоке ЦП на данные массива.|Путем прямого доступа из `array_view` объекта или путем вызова [метод array_view::synchronize](reference/array-view-class.md#synchronize) для непрерывного доступа к данным на исходном контейнере.|  
  
### <a name="shared-memory-with-array-and-arrayview"></a>Общая память для массива и array_view  
 Общая память — это память, может осуществляться ЦП и сочетания клавиш. Использование общей памяти устраняет и значительно сокращает затраты на копирование данных между центральным Процессором и сочетания клавиш. Несмотря на то, что общий объем памяти, он не может получать одновременно ЦП и сочетания клавиш и благодаря этому неопределенное поведение.  
  
 `array` объекты могут использоваться для указания точного управления использование общей памяти, поддерживают связанные сочетаний клавиш. Поддерживает ли ускоритель общей памяти определяется accelerator [supports_cpu_shared_memory](reference/accelerator-class.md#supports_cpu_shared_memory) свойство, которое возвращает `true` при общей памяти поддерживается. Если поддерживается общей памяти, по умолчанию [перечисление access_type](reference/concurrency-namespace-enums-amp.md#access_type) выделения на сочетания клавиш памяти определяется значением `default_cpu_access_type` свойство. По умолчанию `array` и `array_view` принимают объекты на том же `access_type` связанного источника `accelerator`.  
  
 Установив [данных array::cpu_access_type](reference/array-class.md#cpu_access_type) свойство `array` явно, то можно детально упражнения управлять через как общую память используется, оптимизировать приложения для повышения производительности оборудования характеристики на основе шаблонов доступа к памяти ядра его вычисление. `array_view` Отражает же `cpu_access_type` как `array` , она связана с; или, если array_view создается без источника данных, его `access_type` отражает среду, которая сначала вызывает для выделения памяти. То есть, если сначала осуществляется узлом (ЦП), затем он ведет себя как если бы он были созданы через ЦП источника данных и общих папок `access_type` из `accelerator_view` связанные с записью; тем не менее, если это первый доступ `accelerator_view`, затем он ведет себя как если бы он был созданные за `array` создан, `accelerator_view` и общими `array` `access_type`.  
  
 В следующем примере кода показано, как определить ли сочетания клавиш по умолчанию поддерживает общей памяти, а затем создает несколько массивов, имеющих различные cpu_access_type конфигурацию.  
  
```cpp  
#include <amp.h>  
#include <iostream>  
  
using namespace Concurrency;  
  
int main()  
{  
    accelerator acc = accelerator(accelerator::default_accelerator);  
  
    // Early out if the default accelerator doesn’t support shared memory.  
    if (!acc.supports_cpu_shared_memory)  
    {  
        std::cout << "The default accelerator does not support shared memory" << std::endl;  
        return 1;  
    }  
  
    // Override the default CPU access type.  
    acc.default_cpu_access_type = access_type_read_write  
  
    // Create an accelerator_view from the default accelerator. The  
    // accelerator_view inherits its default_cpu_access_type from acc.  
    accelerator_view acc_v = acc.default_view;  
  
    // Create an extent object to size the arrays.  
    extent<1> ex(10);  
  
    // Input array that can be written on the CPU.  
    array<int, 1> arr_w(ex, acc_v, access_type_write);  
  
    // Output array that can be read on the CPU.  
    array<int, 1> arr_r(ex, acc_v, access_type_read);  
  
    // Read-write array that can be both written to and read from on the CPU.  
    array<int, 1> arr_rw(ex, acc_v, access_type_read_write);  
}  
```  
  
## <a name="executing-code-over-data-parallelforeach"></a>Выполнение кода по данным: parallel_for_each  
 [Parallel_for_each](reference/concurrency-namespace-functions-amp.md#parallel_for_each) функция определяет код, который будет выполняться на сочетания клавиш к данным в `array` или `array_view` объекта. Рассмотрим следующий код из введение к этому разделу.  
  
```cpp  
#include <amp.h>  
#include <iostream>  
using namespace concurrency;  
  
void AddArrays() {  
    int aCPP[] = {1, 2, 3, 4, 5};  
    int bCPP[] = {6, 7, 8, 9, 10};  
    int sumCPP[5] = {0, 0, 0, 0, 0};  
  
    array_view<int, 1> a(5, aCPP);  
    array_view<int, 1> b(5, bCPP);  
    array_view<int, 1> sum(5, sumCPP);  
  
    parallel_for_each(  
        sum.extent,   
        [=](index<1> idx) restrict(amp)  
        {  
            sum[idx] = a[idx] + b[idx];  
        }  
    );  
  
    for (int i = 0; i < 5; i++) {  
        std::cout << sum[i] << "\n";  
    }  
}  
```  
  
 `parallel_for_each` Метод принимает два аргумента, домену вычислений и лямбда-выражение.  
  
 *Вычислений домена* — `extent` объекта или `tiled_extent` объект, который определяет множество потоков, чтобы создать для параллельного выполнения. Один поток создается для каждого элемента в домене вычислений. В этом случае `extent` Одномерный объект и имеет пять элементов. Таким образом запускаются пять потоков.  
  
 *Лямбда-выражение* определяет код может выполняться в каждом потоке. Предложение захвата `[=]`, указывает, что тело лямбда-выражение обращается к все захваченные переменные по значению, то в этом случае будут `a`, `b`, и `sum`. В этом примере создается одномерный список параметров `index` переменную с именем `idx`. Значение `idx[0]` равно 0, в первый поток и увеличивает на единицу при каждой последующей потока. `restrict(amp)` Указывает, что используется только подмножество языка C++, может ускорить C++ AMP.  Описываются ограничения на функции, которые имеют модификатор ограничение в [ограничение (C++ AMP)](../../cpp/restrict-cpp-amp.md). Дополнительные сведения см. в разделе, [синтаксис лямбда-выражений](../../cpp/lambda-expression-syntax.md).  
  
 Лямбда-выражение может включать код, выполняемый или он может вызвать функцию отдельных ядра. Необходимо включить функцию ядра `restrict(amp)` модификатор. Следующий пример эквивалентен предыдущему примеру, но он вызывает функцию отдельных ядра.  
  
```cpp  
#include <amp.h>  
#include <iostream>  
using namespace concurrency;  
  
void AddElements(
    index<1> idx,  
    array_view<int, 1> sum,  
    array_view<int, 1> a,  
    array_view<int, 1> b) restrict(amp) {  
    sum[idx] = a[idx] + b[idx];  
}  
  
void AddArraysWithFunction() {  
  
    int aCPP[] = {1, 2, 3, 4, 5};  
    int bCPP[] = {6, 7, 8, 9, 10};  
    int sumCPP[5] = {0, 0, 0, 0, 0};  
  
    array_view<int, 1> a(5, aCPP);  
    array_view<int, 1> b(5, bCPP);  
    array_view<int, 1> sum(5, sumCPP);  
  
    parallel_for_each(  
        sum.extent,   
        [=](index<1> idx) restrict(amp) {  
            AddElements(idx, sum, a, b);  
        }  
    );  
  
    for (int i = 0; i < 5; i++) {  
        std::cout << sum[i] << "\n";  
    }  
}  
```  
  
## <a name="accelerating-code-tiles-and-barriers"></a>Ничто код: Плитки и барьеры  

 Дополнительное ускорение можно получить с помощью мозаичное заполнение. Мозаичное заполнение делит потоков равно прямоугольный подмножества или *плитки*. Определения размера соответствующую плитку на основе набора данных и алгоритм, который используется для кодирования. Для каждого потока имеется доступ к *глобальной* расположение элементов данных относительно весь `array` или `array_view` и доступ к *локального* расположение относительно плитки. С помощью значения индекса локального упрощает код, так как не нужно писать код для преобразования значений индекса из глобального в локальный. Чтобы использовать мозаичное заполнение, вызвать [метод extent::tile](reference/extent-class.md#tile) в домене вычислений в `parallel_for_each` метод и использование [tiled_index](../../parallel/amp/reference/tiled-index-class.md) объекта в лямбда-выражения.  
  
 В обычных приложениях связанные элементы в мозаике иным образом и имеет код для доступа и хранить список значений на плитке. Используйте [ключевое слово tile_static](../../cpp/tile-static-keyword.md) ключевое слово и [метод tile_barrier::wait](reference/tile-barrier-class.md#wait) для выполнения этой задачи. Переменная, имеющая `tile_static` ключевое слово имеет область по всей плитки, и создается экземпляр переменной для каждого элемента мозаики. Необходимо всегда обеспечивать синхронизацию потоков плитки доступа к переменной. [Метод tile_barrier::wait](reference/tile-barrier-class.md#wait) прекращает выполнение текущего потока, пока все потоки в плитке достигнут вызов `tile_barrier::wait`. Поэтому значения могут накапливаться в плитке с помощью `tile_static` переменных. Затем вы можете завершить любых вычислений, которым требуется доступ ко всем значениям.  

  
 Следующая диаграмма представляет двумерный массив данных, которые организованы в плитках выборки.  
  
 ![Индекс значения в разбитом на плитки](../../parallel/amp/media/camptiledgridexample.png "camptiledgridexample")  
  
 В следующем примере кода использует данные выборки из предыдущей диаграммы. Код заменяет каждое значение на плитке среднее значений на плитке.  
  
```cpp  
// Sample data:  
int sampledata[] = {  
    2, 2, 9, 7, 1, 4,  
    4, 4, 8, 8, 3, 4,  
    1, 5, 1, 2, 5, 2,  
    6, 8, 3, 2, 7, 2};  
 
// The tiles:  
// 2 2    9 7    1 4  
// 4 4    8 8    3 4  
//  
// 1 5    1 2    5 2  
// 6 8    3 2    7 2  
 
// Averages:  
int averagedata[] = {   
    0, 0, 0, 0, 0, 0,   
    0, 0, 0, 0, 0, 0,   
    0, 0, 0, 0, 0, 0,   
    0, 0, 0, 0, 0, 0,   
};  
 
array_view<int, 2> sample(4, 6, sampledata);

array_view<int, 2> average(4, 6, averagedata);  
  
parallel_for_each(  
    // Create threads for sample.extent and divide the extent into 2 x 2 tiles.  
    sample.extent.tile<2,2>(), 
        [=](tiled_index<2,2> idx) restrict(amp) { 
        // Create a 2 x 2 array to hold the values in this tile.  
        tile_static int nums[2][2];  

        // Copy the values for the tile into the 2 x 2 array.  
        nums[idx.local[1]][idx.local[0]] = sample[idx.global];  

        // When all the threads have executed and the 2 x 2 array is complete, find the average.  
        idx.barrier.wait();  
        int sum = nums[0][0] + nums[0][1] + nums[1][0] + nums[1][1];

        // Copy the average into the array_view.  
        average[idx.global] = sum / 4;  
    });
  
for (int i = 0; i <4; i++) {  
    for (int j = 0; j <6; j++) {  
        std::cout << average(i,j) << " ";  
    }  
    std::cout << "\n";  
}  
 
// Output:  
// 3 3 8 8 3 3  
// 3 3 8 8 3 3  
// 5 5 2 2 4 4  
// 5 5 2 2 4 4  
```  
  
## <a name="math-libraries"></a>Математические библиотеки  
 C++ AMP содержит две математические библиотеки. Библиотека двойной точности в [имен Concurrency::precise_math](../../parallel/amp/reference/concurrency-precise-math-namespace.md) обеспечивает поддержку функций двойной точности. Он также обеспечивает поддержку для функций одиночной точности, несмотря на то, что по-прежнему необходима поддержка двойной точности на оборудовании. Он соответствует [спецификации C99 (ISO/IEC 9899)](http://go.microsoft.com/fwlink/p/?linkid=225887). Сочетания клавиш, должны поддерживать полной двойной точности. Можно определить, является ли это делается путем проверки значения [данных accelerator::supports_double_precision](reference/accelerator-class.md#supports_double_precision). Быстрый математическую библиотеку в [имен Concurrency::fast_math](../../parallel/amp/reference/concurrency-fast-math-namespace.md), содержит другой набор математических функций. Эти функции, которые поддерживают только `float` операндов, выполняться гораздо быстрее, но не такой точный результат, что и в число двойной точности в математическую библиотеку. Функции, содержащиеся в \<amp_math.h > заголовок файла и всех объявлены с `restrict(amp)`. Функции в \<cmath > файла заголовка, импортируются в обоих `fast_math` и `precise_math` пространства имен. `restrict` Ключевое слово используется для различения \<cmath > версия и версия C++ AMP. В следующем коде вычисляется логарифм по основанию 10, с помощью быстрый метод, для каждого значения, которое находится в домене вычислений.  

  
```cpp  
#include <amp.h>  
#include <amp_math.h>  
#include <iostream>  
using namespace concurrency;  
  
void MathExample() {  
  
    double numbers[] = { 1.0, 10.0, 60.0, 100.0, 600.0, 1000.0 };  
    array_view<double, 1> logs(6, numbers);  
  
    parallel_for_each(  
        logs.extent,  
 [=] (index<1> idx) restrict(amp) {  
            logs[idx] = concurrency::fast_math::log10(logs[idx]);  
        }  
    );  
  
    for (int i = 0; i < 6; i++) {  
        std::cout << logs[i] << "\n";  
    }  
}  
  
```  
  
## <a name="graphics-library"></a>Библиотека графики  
 C++ AMP включает в себя графическую библиотеку, предназначенный для графическим ускорителем программирования. Эта библиотека используется только на устройствах, поддерживающих native графическим функциям. Методы, в [пространство имен Concurrency::graphics](../../parallel/amp/reference/concurrency-graphics-namespace.md) и содержащихся в \<amp_graphics.h > файла заголовка. Ключевыми компонентами графической библиотеки являются:  
  
- [Класс Texture](../../parallel/amp/reference/texture-class.md): класс текстуры можно использовать для создания текстур из памяти или из файла. Текстуры аналогичны массивов, поскольку они содержат данные, и они напоминают контейнеров в стандартной библиотеке C++ в отношении назначения и конструкцией копирования. Дополнительные сведения см. в разделе [Контейнеры стандартной библиотеки C++](../../standard-library/stl-containers.md). Параметры шаблона для `texture` класс — это тип элемента и ранг. Ранг может быть 1, 2 или 3. Тип элемента может быть одним из типов короткого вектора, которые описаны далее в этой статье.  
  
- [Класс writeonly_texture_view](../../parallel/amp/reference/writeonly-texture-view-class.md): предоставляет доступ только для записи в любые текстуры.  
  
- [Короткий вектор библиотеки](http://msdn.microsoft.com/en-us/4c4f5bed-c396-493b-a238-c347563f645f): Определяет набор типов короткого вектора длины 2, 3 и 4 на основе `int`, `uint`, `float`, `double`, [norm](../../parallel/amp/reference/norm-class.md), или [unorm](../../parallel/amp/reference/unorm-class.md).  
  
## <a name="universal-windows-platform-uwp-apps"></a>Приложений платформы (UWP) для универсальных приложений Windows  
 Как и другие библиотеки C++ можно использовать C++ AMP в приложениях UWP. Эти статьи описывают включить код C++ AMP в приложениях, созданный с помощью C++, C#, Visual Basic или JavaScript.  
  
- [Использование C++ AMP в приложениях UWP](../../parallel/amp/using-cpp-amp-in-windows-store-apps.md)  
  
- [Пошаговое руководство: Создание базового компонента среды выполнения Windows в C++ и вызов его из JavaScript](http://go.microsoft.com/fwlink/p/?linkid=249077)  
  
- [Bing Maps Trip Optimizer — приложение магазина Windows на JavaScript и C++](http://go.microsoft.com/fwlink/p/?linkid=249078)  
  
- [Как использовать C++ AMP из C# с помощью среды выполнения Windows](http://go.microsoft.com/fwlink/p/?linkid=249080)  
  
- [Как использовать C++ AMP из C#](http://go.microsoft.com/fwlink/p/?linkid=249081)  
  
- [Вызов неуправляемых функций из управляемого кода](../../dotnet/calling-native-functions-from-managed-code.md)  
  
## <a name="c-amp-and-concurrency-visualizer"></a>C++ AMP и визуализатор параллелизма  
 Визуализатор параллелизма поддерживает анализ производительности кода C++ AMP. Эти функции описаны в следующих статьях:  
  
- [Граф активности GPU](/visualstudio/profiling/gpu-activity-graph)  
  
- [Активность GPU (подкачка)](/visualstudio/profiling/gpu-activity-paging)  
  
- [Активность GPU (этот процесс)](/visualstudio/profiling/gpu-activity-this-process)  
  
- [Активность GPU (другие процессы)](/visualstudio/profiling/gpu-activity-other-processes)  
  
- [Каналы (представление "Потоки")](/visualstudio/profiling/channels-threads-view)  
  
- [Анализ кода C++ AMP с помощью визуализатора параллелизма](http://go.microsoft.com/fwlink/p/?linkid=253987&clcid=0x409)  
  
## <a name="performance-recommendations"></a>Рекомендации по повышению производительности  
 Остатка от деления и деление целых чисел без знака обладают значительно лучшей производительностью, чем модуля и деления целых чисел со знаком. Мы рекомендуем использовать целых чисел без знака по возможности.  
  
## <a name="see-also"></a>См. также  
 [C++ AMP (C++ Accelerated Massive Parallelism)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)   
 [Синтаксис лямбда-выражений](../../cpp/lambda-expression-syntax.md)   
 [Справочник (C++ AMP)](../../parallel/amp/reference/reference-cpp-amp.md)   
 [Параллельное программирование в блоге машинного кода](http://go.microsoft.com/fwlink/p/?linkid=238472)
