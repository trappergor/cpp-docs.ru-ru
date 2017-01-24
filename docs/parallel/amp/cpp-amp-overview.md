---
title: "Общие сведения о C++ AMP | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C++ Accelerated Massive Parallelism, требования"
  - "C++ Accelerated Massive Parallelism, архитектура"
  - "C++ AMP"
  - "C++ Accelerated Massive Parallelism, общие сведения"
  - "C++ Accelerated Massive Parallelism"
ms.assetid: 9e593b06-6e3c-43e9-8bae-6d89efdd39fc
caps.latest.revision: 60
caps.handback.revision: 60
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Общие сведения о C++ AMP
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

C++ Accelerated Massive Parallelism (C++ AMP) ускоряют выполнение кода C++, используя преимущества данных параллельного оборудования, такого как графический процессор (GPU) на выделенной видеокарте. С помощью C++ AMP, можно составить код алгоритмы многомерных данных таким образом, можно ускорить выполнение с помощью параллелизма на разнородное оборудование. Модель программирования C++ AMP входят многомерные массивы, индексирования, передачи памяти, заполнения и библиотека математических функций. Расширения языка C++ AMP можно использовать для управления как данные перемещаются из ЦП GPU и обратно, таким образом, можно повысить производительность.  
  
## <a name="system-requirements"></a>Требования к системе  
  
- [!INCLUDE[win7](../../build/includes/win7_md.md)], [!INCLUDE[win8](../../build/includes/win8_md.md)], [!INCLUDE[winsvr08_r2](../Token/winsvr08_r2_md.md)] или [!INCLUDE[winserver8](../../build/includes/winserver8_md.md)]  
  
-   Функция уровень DirectX 11 11.0 или более поздней версии оборудования  
  
-   Для отладки в программном эмуляторе [!INCLUDE[win8](../../build/includes/win8_md.md)] или [!INCLUDE[winserver8](../../build/includes/winserver8_md.md)] не требуется. Для отладки на оборудовании необходимо установить драйверы для видеокарты. Дополнительные сведения см. в разделе [отладки кода GPU](../Topic/Debugging%20GPU%20Code.md).  
  
## <a name="introduction"></a>Вступление  
 В следующих двух примерах показаны основные компоненты C++ AMP. Предположим, что необходимо добавить соответствующие элементы двух одномерных массивов. Например, может потребоваться добавить `{1, 2, 3, 4, 5}` и `{6, 7, 8, 9, 10}` для получения `{7, 9, 11, 13, 15}`. Без использования C++ AMP, можно написать следующий код для суммирования и отображения результатов.  
  
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
  
-   Данные: Данные состоят из трех массивов. Все имеют те же ранга (один) и длина (5).  
  
-   Итерации: Первый `for` цикл предоставляет механизм для перебора элементов в массивах. В первом содержится код, который требуется выполнить для вычисления суммы `for` блок.  
  
-   Индекс: `idx` переменная получает доступ к отдельным элементам массивов.  
  
 Использование C++ AMP, можно написать следующий код вместо.  
  
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
 [=](index<1> idx) restrict(amp)  
    {  
        sum[idx] = a[idx] + b[idx];  
    }  
    );  
  
    // Print the results. The expected output is "7, 9, 11, 13, 15".  
    for (int i = 0; i < size; i++) {  
        std::cout << sum[i] << "\n";  
    }  
}  
  
```  
  
 Те же основные элементы присутствуют, но C++ AMP конструкции используются:  
  
-   Данные: Можно использовать массивы C++ для создания трех C++ AMP [array_view](../../parallel/amp/reference/array-view-class.md) объектов. Необходимо указать четыре значения для создания `array_view` объекта: значения данных, ранг, тип элемента и длина `array_view` объекта в каждом измерении. Ранг и тип передаются как параметры типа. Данные и длину, передаются как параметры конструктора. В этом примере массив C++, который передается в конструктор является одномерным массивом. Ранг и длина используются для создания прямоугольную форму данных в `array_view` объекта и данные значения используются для заполнения массива. Также включает библиотеку времени выполнения [класс array](../../parallel/amp/reference/array-class.md), который имеет интерфейс, который напоминает `array_view` класса и рассматривается далее в этой статье.  
  
-   Итерации: [функция parallel_for_each (C++ AMP)](../Topic/parallel_for_each%20Function%20\(C++%20AMP\).md) предоставляет механизм для перебора элементов данных, или *вычислений домена*. В этом примере определяется домене вычислений `sum.extent`. Содержится код, который должен выполняться в лямбда-выражение или *функция ядра*.  `restrict(amp)` Указывает, что используется только подмножество языка C++, может ускорить C++ AMP.  
  
-   Индекс: [класс index](../../parallel/amp/reference/index-class.md) переменной, `idx`, объявленные с рангом 1 соответствуют ранг `array_view` объекта. При наличии индекса обеспечивает доступ к отдельным элементам `array_view` объектов.  
  
## <a name="shaping-and-indexing-data-index-and-extent"></a>Формирования и индексации данных: индекс и степени  
 Необходимо указать значения данных и объявить форму данных перед запуском кода ядра. Все данные определяются как массив (прямоугольный), и можно определить массив будет иметь любой ранг (размерность). Данные могут быть любого размера в любое из измерений.  
  
### <a name="index-class"></a>Класс index  
  [Класс index](../../parallel/amp/reference/index-class.md) Указывает расположение в `array` или `array_view` объекта, инкапсулируя смещение от начала координат в каждом измерении в один объект. При доступе к расположение в массиве, передайте `index` объекта для индексирования оператор `[]`, вместо списка индексов целое число со знаком. Доступ к элементам в каждом измерении с помощью [оператор array:: operator()](../Topic/array::operator\(\)%20Operator.md) или [оператор array_view:: operator()](../Topic/array_view::operator\(\)%20Operator.md).  
  
 В следующем примере создается одномерный индекс, который задает третий элемент в одномерном массиве `array_view` объекта. Индекс используется для печати третьего элемента в `array_view` объекта. Выходные данные — 3.  
  
```cpp  
 
int aCPP[] = {1, 2, 3, 4, 5};  
array_view<int, 1> a(5, aCPP);

index<1> idx(2);

std::cout <<a[idx] <<"\n";    
// Output: 3  
 
```  
  
 В следующем примере создается двухмерный индекс, указывающий элемент где строка = 1 и столбце = 2 в двухмерный `array_view` объекта. Первый параметр в `index` конструктор — это компонент строки, а второй параметр — это компонент столбца. Выходные данные — 6.  
  
```cpp  
 
int aCPP[] = {1, 2, 3,  
    4, 5, 6};  
array_view<int, 2> a(2, 3, aCPP);

index<2> idx(1, 2);

std::cout <<a[idx] <<"\n";  
// Output: 6  
 
```  
  
 В следующем примере создается трехмерный индекс, указывающий элемент где глубина = 0, строки = 1, а столбец = 3 в трехмерный массив `array_view` объекта. Обратите внимание, что первый параметр — это компонент глубины, второй параметр — это компонент строки третий параметр — это компонент столбца. Выходные данные — 8.  
  
```cpp  
 
int aCPP[] = {  
    1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12,   
    1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12};  
 
array_view<int, 3> a(2, 3, 4, aCPP);

// Specifies the element at 3, 1, 0.  
index<3> idx(0, 1, 3);

std::cout <<a[idx] <<"\n";  
 
// Output: 8  
 
```  
  
### <a name="extent-class"></a>Класс extent  
  [Экстент класс](../Topic/extent%20Class%20\(C++%20AMP\).md) задает длину данных в каждом измерении `array` или `array_view` объекта. Можно создать экстент и использовать его для создания `array` или `array_view` объекта. Также можно получить текущую область `array` или `array_view` объекта. В следующем примере выводится длина экстента в каждом измерении `array_view` объекта.  
  
```cpp  
 
int aCPP[] = {  
    1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12,   
    1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12};  
// There are 3 rows and 4 columns, and the depth is two.  
array_view<int, 3> a(2, 3, 4, aCPP);

std::cout <<"The number of columns is " <<a.extent[2] <<"\n";  
std::cout <<"The number of rows is " <<a.extent[1] <<"\n";  
std::cout <<"The depth is " <<a.extent[0]<<"\n";  
std::cout <<"Length in most significant dimension is " <<a.extent[0] <<"\n";  
 
```  
  
 В следующем примере создается `array_view` объект, который имеет те же измерения как объект в предыдущем примере, но в этом примере используется `extent` объекта вместо явной передачи параметров в `array_view` конструктора.  
  
```cpp  
 
int aCPP[] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24};  
extent<3> e(2, 3, 4);

array_view<int, 3> a(e, aCPP);

std::cout <<"The number of columns is " <<a.extent[2] <<"\n";  
std::cout <<"The number of rows is " <<a.extent[1] <<"\n";  
std::cout <<"The depth is " <<a.extent[0] <<"\n";  
 
```  
  
## <a name="moving-data-to-the-accelerator-array-and-arrayview"></a>Сочетания клавиш перемещения данных: массив и array_view  
 В библиотеке времени выполнения определяются два контейнера данных, используемые для перемещения данных в сочетания клавиш. Они являются [класс array](../../parallel/amp/reference/array-class.md) и [класс array_view](../../parallel/amp/reference/array-view-class.md).  `array` Класса является класс контейнера, который создает глубокую копию данных, при создании объекта.  `array_view` Класса является класс-оболочку, которая копирует данные, когда функция ядра обращается к данным. Если данные, необходимые на исходном устройстве данные копируются обратно.  
  
### <a name="array-class"></a>Класс array  
 Если `array` объект создан, глубокую копию данных создается на сочетания клавиш, если вы используете конструктор, который включает указатель на набор данных. Функция ядра изменяет копии на сочетания клавиш. После завершения выполнения функции ядра, необходимо скопировать данные обратно к структуре источника данных. Этот пример умножает каждый элемент в векторе 10. После завершения функции ядра [вектор оператор преобразования]--brokenlink--(.. /Topic/Array::operator%20std::Vector%3Cvalue_type%3E%20Operator.MD)Is используется для копирования данных обратно в объекте vector.  
  
```cpp  
 
std::vector<int> data(5);

for (int count = 0; count <5; count++)   
{  
    data[count] = count;  
}  
 
array<int, 1> a(5, data.begin(), data.end());

 
parallel_for_each(
    a.extent, 
 [=, &a](index<1> idx) restrict(amp)  
 {  
    a[idx] = a[idx]* 10;  
 });

 
data = a;  
for (int i = 0; i <5; i++)   
{  
    std::cout <<data[i] <<"\n";  
}  
 
```  
  
### <a name="arrayview-class"></a>Класс array_view  
  `array_view` Содержит практически те же члены, как `array` класс, но это не соответствует. Данные, передаваемые `array_view` конструктор не реплицируются на GPU, как в случае с `array` конструктор. Вместо этого данные копируются ускоритель при выполнении функции ядра. Таким образом Если необходимо создать два `array_view` объекты, которые используют те же данные и `array_view` объекты ссылаются на одно и то же пространство памяти. При этом необходимо синхронизировать все многопоточного доступа. Основное преимущество использования `array_view` класс является перемещаются данные только в том случае, если это необходимо.  
  
### <a name="comparison-of-array-and-arrayview"></a>Сравнение массивов и array_view  
 В следующей таблице показаны сходства и различия между `array` и `array_view` классы.  
  
|Описание|array - класс|array_view - класс|  
|-----------------|-----------------|-----------------------|  
|Когда определяется ранг|Во время компиляции.|Во время компиляции.|  
|Если определить экстент|Во время выполнения.|Во время выполнения.|  
|Фигура|Прямоугольный.|Прямоугольный.|  
|Хранилище данных|— Это контейнер данных.|Представляет оболочку данных.|  
|Копировать|Явные и глубокую копию определения.|Неявные копирования при доступе с помощью функции ядра.|  
|Получение данных|Путем копирования данных массива объекта на поток ЦП.|Путем прямого доступа из `array_view` объекта или путем вызова [метод array_view::synchronize](../Topic/array_view::synchronize%20Method.md) для дальнейшего доступа к данным на исходном контейнере.|  
  
### <a name="shared-memory-with-array-and-arrayview"></a>Общая память массива и array_view  
 Общая память — это память, может осуществляться с Процессором и сочетания клавиш. Использование общей памяти устраняет или значительно уменьшает расходы на копирование данных между центральным Процессором и сочетания клавиш. Несмотря на то, что общий объем памяти, он не доступен одновременно центральным Процессором и сочетания клавиш, и благодаря этому поведение не определено.  
  
 `array` объекты могут использоваться для указания детальный контроль использования общей памяти, если связанный accelerator поддерживает его. Поддерживает ли ускоритель общей памяти определяется accelerator [supports_cpu_shared_memory](../Topic/accelerator::supports_cpu_shared_memory%20Data%20Member.md) свойство, которое возвращает `true` при общей памяти поддерживается. Если поддерживается общей памяти, по умолчанию [перечисление access_type](../Topic/access_type%20Enumeration.md) для памяти определяется выделения на ускорителе `default_cpu_access_type` свойство. По умолчанию `array` и `array_view` Объекты принимают на том же `access_type` с основной связанные `accelerator`.  
  
 Установив [данных array::cpu_access_type](../Topic/array::cpu_access_type%20Data%20Member.md) Свойства `array` явно, то можно упражнения точного управления через как общую память используется, можно оптимизировать приложение для характеристики производительности оборудования, на основе шаблонов доступа к памяти, его вычислительных ядер.  `array_view` Же отражает `cpu_access_type` как `array` он связан; или, если array_view создается без источника данных его `access_type` отражает среду, которая сначала вызывает его для выделения памяти. То есть, если сначала осуществляется узлом (ЦП), затем его поведение соответствует поведению созданных по источнику данных ЦП и общих папок `access_type` из `accelerator_view` связанные с захвата; тем не менее, если это первый доступ `accelerator_view`, то он ведет себя так, как если бы он были созданы через `array` создан, `accelerator_view` и общие папки `array`в `access_type`.  
  
 В следующем примере кода показано, как определить сочетания клавиш по умолчанию поддерживает общей памяти и затем создает несколько массивов, которые имеют различные cpu_access_type конфигурации.  
  
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
  [Parallel_for_each](../Topic/parallel_for_each%20Function%20\(C++%20AMP\).md) функция определяет код, который вы хотите запустить на сочетания клавиш к данным в `array` или `array_view` объекта. Рассмотрим следующий код с появлением в этом разделе.  
  
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
  
  *Вычислений домена* — `extent` объекта или `tiled_extent` объект, который определяет набор потоков, чтобы создать для параллельного выполнения. Один поток создается для каждого элемента в домене вычислений. В этом случае `extent` объект является одномерным массивом и содержит пять элементов. Таким образом запускаются пять потоков.  
  
  *Лямбда-выражение* определяет код может выполняться в каждом потоке. Предложение захвата `[=]`, указывает, что тело лямбда-выражения осуществляет доступ к всем записанным переменным по значению, который в данном случае `a`, `b`, и `sum`. В этом примере создается одномерный список параметров `index` переменной с именем `idx`. Значение `idx[0]` равно 0 в первый поток и увеличивается на единицу в каждой последующей потока.  `restrict(amp)` Указывает, что используется только подмножество языка C++, может ускорить C++ AMP.  Описываются ограничения на функции, которые имеют модификатор ограничение в [ограничение (C++ AMP)](../../cpp/restrict-cpp-amp.md). Дополнительные сведения см. в [синтаксис лямбда-выражений](../../cpp/lambda-expression-syntax.md).  
  
 Лямбда-выражение может включать код, выполняемый или оно может вызвать функцию отдельных ядра. Необходимо включить функцию ядра `restrict(amp)` модификатор. Следующий пример является эквивалентом в предыдущем примере, но он вызывает функцию отдельных ядра.  
  
```cpp  
  
#include <amp.h>  
#include <iostream>  
using namespace concurrency;  
  
void AddElements(index<1> idx, array_view<int, 1> sum, array_view<int, 1> a, array_view<int, 1> b) restrict(amp)  
{  
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
 [=](index<1> idx) restrict(amp)  
        {  
            AddElements(idx, sum, a, b);  
        }  
    );  
  
    for (int i = 0; i < 5; i++) {  
        std::cout << sum[i] << "\n";  
    }  
}  
  
```  
  
## <a name="accelerating-code-tiles-and-barriers"></a>Растет код: Плитки и барьеры  
 Дополнительное ускорение можно получить с помощью мозаики. Мозаичное заполнение потоков разбивается на подмножества равно прямоугольный или *плитки*. Определите размер соответствующего мозаики, на основе набора данных и алгоритм, который используется для кодирования. Для каждого потока есть доступ к *глобальной* расположение элементов данных относительно весь `array` или `array_view` и доступ к *локального* расположение относительно карточки. С помощью значения индекса локального упрощает код, так как не нужно писать код для преобразования значения индекса из глобального в локальный. Использование мозаичного заполнения, вызовите [метод extent::tile](../Topic/extent::tile%20Method.md) в домене вычислений в `parallel_for_each` метод и использование [tiled_index](../../parallel/amp/reference/tiled-index-class.md) объекта в лямбда-выражение.  
  
 В обычных приложениях связанные элементы в мозаике каким-либо образом и имеет код для доступа и отслеживать значения на плитке. Используйте [ключевое слово tile_static](../Topic/tile_static%20Keyword.md) ключевое слово и [метод tile_barrier::wait](../Topic/tile_barrier::wait%20Method.md) для выполнения этой задачи. Переменную, которая имеет `tile_static` ключевое слово имеет область в рамках всей мозаики, и создается экземпляр переменной для каждого элемента мозаики. Необходимо обрабатывать синхронизации потоков плитки доступа к переменной.  [Метод tile_barrier::wait](../Topic/tile_barrier::wait%20Method.md) прекращает выполнение текущего потока, пока все потоки в плитке достигнут вызов `tile_barrier::wait`. Поэтому можно накапливания значений в плитке с помощью `tile_static` переменных. Затем можно завершить любых вычислений, которым требуется доступ ко всем значениям.  
  
 Следующая диаграмма представляет двумерный массив данных, расположенных на плитках выборки.  
  
 ![Значения индекса в пространстве, разбитом на плитки](../../parallel/amp/media/camptiledgridexample.png "CampTiledGridExample")  
  
 В следующем примере кода данные выборки из предыдущей диаграммы. Код заменяет каждое значение в плитке на среднее арифметическое значений на плитке.  
  
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

 
parallel_for_each(*// Create threads for sample.extent and divide the extent into 2 x 2 tiles.  
    sample.extent.tile<2,2>(), 
 [=](tiled_index<2,2> idx) restrict(amp)  
 { *// Create a 2 x 2 array to hold the values in this tile.  
    tile_static int nums[2][2]; *// Copy the values for the tile into the 2 x 2 array.  
    nums[idx.local[1]][idx.local[0]] = sample[idx.global]; *// When all the threads have executed and the 2 x 2 array is complete, find the average.  
    idx.barrier.wait();
int sum = nums[0][0] + nums[0][1] + nums[1][0] + nums[1][1]; *// Copy the average into the array_view.  
    average[idx.global] = sum / 4;  
 });

 
for (int i = 0; i <4; i++) {  
    for (int j = 0; j <6; j++) {  
    std::cout <<average(i,j) <<" ";  
 }  
    std::cout <<"\n";  
}  
 
// Output:  
// 3 3 8 8 3 3  
// 3 3 8 8 3 3  
// 5 5 2 2 4 4  
// 5 5 2 2 4 4  
 
```  
  
## <a name="math-libraries"></a>Математические библиотеки  
 C++ AMP включает два математических библиотек. Библиотека двойной точности в [имен Concurrency::precise_math](../Topic/Concurrency::precise_math%20Namespace.md) обеспечивает поддержку для функций двойной точности. Он также поддерживает функции одиночной точности, несмотря на то, что по-прежнему необходима поддержка двойной точности на оборудовании. Он соответствует [спецификации C99 (ISO/IEC 9899)](http://go.microsoft.com/fwlink/LinkId=225887). Сочетания клавиш должен поддерживать полный двойной точности. Можно определить, является ли выполняется путем проверки значения [данных accelerator::supports_double_precision](../Topic/accelerator::supports_double_precision%20Data%20Member.md). Быстрое математических библиотек в [имен Concurrency::fast_math](../../parallel/amp/reference/concurrency-fast-math-namespace.md), содержит другой набор математических функций. Эти функции, которые поддерживают только `float` операндов, выполняться гораздо быстрее, но не с точностью до их в библиотеку math двойной точности. Функции содержатся в файле заголовка \< amp_math.h > и всех объявлены с `restrict(amp)`. Функции в \< cmath> заголовочный файл импортируется как `fast_math` и `precise_math` пространства имен.  `restrict` Ключевое слово используется для различения \< cmath> версию и C++ AMP. В следующем коде вычисляется логарифм по основанию 10, используя метод быстрого каждого значения в домене вычислений.  
  
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
  
## <a name="graphics-library"></a>Графическая библиотека  
 C++ AMP включает библиотеку графики, предназначенный для ускоренной программировании графики. Эта библиотека используется только на устройствах, поддерживающих собственный графические функции. Методы, в [имен Concurrency::graphics](../../parallel/amp/reference/concurrency-graphics-namespace.md) и содержатся в файле заголовка \< amp_graphics.h >. Ключевыми компонентами графической библиотеки являются:  
  
- [Класс Texture](../Topic/texture%20Class.md): можно использовать класс текстуры создание текстуры из памяти или из файла. Текстуры похожие на массивы, так как они содержат данные они напоминают контейнеры в стандартных шаблонов библиотеки (STL) с точки зрения присваивания и конструктора копии. Дополнительные сведения см. в разделе [контейнеры STL](../../standard-library/stl-containers.md). Параметры шаблона `texture` класс — это тип элемента и ранг. Ранг может быть 1, 2 или 3. Тип элемента может быть один из типов короткого вектора, описанных далее в этой статье.  
  
- [Класс writeonly_texture_view](../Topic/writeonly_texture_view%20Class.md): предоставляет доступ только для записи к любой текстуры.  
  
- [Короткий вектор библиотеки](http://msdn.microsoft.com/ru-ru/4c4f5bed-c396-493b-a238-c347563f645f): Определяет набор типов короткого вектора длиной 2, 3 и 4, основанные на `int`, `uint`, `float`, `double`, [нормы](../../parallel/amp/reference/norm-class.md), или [unorm](../../parallel/amp/reference/unorm-class.md).  
  
## <a name="includewin8appnamelongtokenwin8appnamelongmdmd-apps"></a>Приложения [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]  
 Как и другие библиотеки C++ можно использовать C++ AMP в вашей [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] приложений. Эти статьи описывается, как включить код C++ AMP в приложениях, созданных с помощью C++, C#, Visual Basic или JavaScript:  
  
- [Использование C++ AMP в приложениях для магазина Windows](../../parallel/amp/using-cpp-amp-in-windows-store-apps.md)  
  
- [Пошаговое руководство: Создание базового компонента среды выполнения Windows на C++ и вызов его из JavaScript](http://go.microsoft.com/fwlink/p/LinkId=249077)  
  
- [Bing Maps Trip Optimizer, окно магазина на JavaScript и C++](http://go.microsoft.com/fwlink/p/LinkId=249078)  
  
- [Использование C++ AMP из C# с помощью среды выполнения Windows](http://go.microsoft.com/fwlink/p/LinkId=249080)  
  
- [Использование C++ AMP с C#](http://go.microsoft.com/fwlink/p/LinkId=249081)  
  
- [Вызов неуправляемых функций из управляемого кода](../../dotnet/calling-native-functions-from-managed-code.md)  
  
## <a name="c-amp-and-concurrency-visualizer"></a>C++ AMP и визуализатор параллелизма  
 Визуализатор параллелизма поддерживает анализ производительности кода C++ AMP. Эти функции описываются в следующих статьях:  
  
- [Граф активности GPU](../Topic/GPU%20Activity%20Graph.md)  
  
- [Активность GPU (подкачка)](../Topic/GPU%20Activity%20\(Paging\).md)  
  
- [Активность GPU (этот процесс)](../Topic/GPU%20Activity%20\(This%20Process\).md)  
  
- [Активность GPU (другие процессы)](../Topic/GPU%20Activity%20\(Other%20Processes\).md)  
  
- [Каналы (представление "Потоки")](../Topic/Channels%20\(Threads%20View\).md)  
  
- [Анализ кода C++ AMP с помощью визуализатора параллелизма](http://go.microsoft.com/fwlink/LinkID=253987&clcid=0x409)  
  
## <a name="performance-recommendations"></a>Рекомендации по повышению производительности  
 Остатка от деления и деление целых чисел без знака иметь лучшую производительность, чем остатка от деления и деления целых чисел со знаком. Корпорация Майкрософт рекомендует использовать целых, когда это возможно.  
  
## <a name="see-also"></a>См. также раздел  
 [C++ AMP (C++ Accelerated Massive Parallelism)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)   
 [Синтаксис лямбда-выражений](../../cpp/lambda-expression-syntax.md)   
 [Справочник (C++ AMP)](../../parallel/amp/reference/reference-cpp-amp.md)   
 [Параллельное программирование в блоге машинного кода](http://go.microsoft.com/fwlink/p/LinkId=238472)
