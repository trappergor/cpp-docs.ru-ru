---
title: Общие сведения о C++ AMP | Документация Майкрософт
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
ms.openlocfilehash: f7cbfd0e8b9ef95aac083b367980571c5535e6a7
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42599046"
---
# <a name="c-amp-overview"></a>Общие сведения о C++ AMP
C++ Accelerated Massive Parallelism (C++ AMP) ускоряет выполнение кода C++, использование преимуществ оборудования параллельной обработки данных, таких как графический процессор (GPU) на выделенной видеокарте. С помощью C++ AMP, можно составить код алгоритмы многомерных данных таким образом, чтобы выполнение может быть ускорено с помощью параллелизма на различном оборудовании. Модель программирования C++ AMP включает многомерные массивы, индексирование, перенос памяти, мозаичное заполнение и библиотеку математических функций. Расширения языка C++ AMP можно использовать для управления, как данные перемещаются из ЦП в GPU и обратно, так что можно улучшить производительность.  
  
## <a name="system-requirements"></a>Требования к системе  
  
- Windows 7, Windows 8, Windows Server 2008 R2 или Windows Server 2012  
  
- DirectX 11 с уровнем компонентов 11.0 или более поздней версии оборудования  
  
- Для отладки на программном эмуляторе Windows 8 или Windows Server 2012 является обязательным. Для отладки на оборудовании необходимо установить драйверы для видеокарты. Дополнительные сведения см. в разделе [отладка кода GPU](/visualstudio/debugger/debugging-gpu-code).  
  
## <a name="introduction"></a>Вступление  
 
В следующих двух примерах показаны основные компоненты C++ AMP. Предположим, что вы хотите добавить соответствующие элементы двух одномерных массивов. Например, может потребоваться добавить `{1, 2, 3, 4, 5}` и `{6, 7, 8, 9, 10}` для получения `{7, 9, 11, 13, 15}`. Без использования C++ AMP, можно написать следующий код для добавления чисел и отображения результатов.  
  
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
  
- Данные: Данные состоят из трех массивов. Все имеют те же ранг (один) и длину (пять).  
  
- Перебор: Первый `for` цикл предоставляет механизм для перебора элементов в массивах. Код, который должен выполняться для вычисления суммы содержится в первом `for` блока.  
  
- Индекс: `idx` переменная обращается к отдельным элементам массивов.  
  
 Использование C++ AMP, можно написать следующий код вместо этого.  
  
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
  
- Данные: Используйте массивы C++ для создания трех C++ AMP [array_view](../../parallel/amp/reference/array-view-class.md) объектов. Необходимо указать четыре значения для создания `array_view` объект: значения данных, ранг, тип элемента и длину `array_view` в каждом измерении. Ранг и тип передаются как параметры типа. Данные и длина передаются в качестве параметров конструктора. В этом примере массив C++, который передается в конструктор является одномерным. Ранг и длина используются для построения прямоугольной формы данных в `array_view` объект и данные значения используются для заполнения массива. Библиотека среды выполнения включает также [класс array](../../parallel/amp/reference/array-class.md), который содержит интерфейс, похожий на `array_view` класса и рассматривается далее в этой статье.  
  
- Итерация: [parallel_for_each функции (C++ AMP)](reference/concurrency-namespace-functions-amp.md#parallel_for_each) предоставляет механизм для перебора элементов данных, или *вычислительный домен*. В этом примере задается вычислительного домена `sum.extent`. Содержится код, который должен выполняться в лямбда-выражения, или *функция ядра*. `restrict(amp)` Указывает, что используется только то подмножество языка C++, которого может ускорить C++ AMP.  
  
- Индекс: [класса индекса](../../parallel/amp/reference/index-class.md) переменной, `idx`, объявленный с рангом, соответствующим рангу объекта `array_view` объекта. С помощью индекса, можно получить доступ к отдельным элементам `array_view` объектов.  
  
## <a name="shaping-and-indexing-data-index-and-extent"></a>Формирование и индексирование данных: индекс и границы  
 
Необходимо задать значения данных и объявить форму данных перед выполнением кода ядра. Все данные определены как массив (прямоугольный), и можно задать массив любого ранга (число измерений). Данные могут быть любого размера в любом из измерений.  
  
### <a name="index-class"></a>Класс index  
[Класса индекса](../../parallel/amp/reference/index-class.md) указывает местоположение в `array` или `array_view` , инкапсулируя смещение от начала координат в каждом измерении в один объект. Когда вы обращаетесь в расположение в массиве, передается `index` объект оператору индексирования `[]`, вместо списка целочисленных индексов. Доступ к элементам в каждом измерении с помощью [оператор array:: operator()](reference/array-class.md#operator_call) или [оператор array_view:: operator()](reference/array-view-class.md#operator_call).  
  
В следующем примере создается одномерный индекс, который задает третий элемент одномерного массива `array_view` объекта. Индекс используется для печати третьего элемента в `array_view` объекта. Результат: 3.  
  
```cpp  
int aCPP[] = {1, 2, 3, 4, 5};  
array_view<int, 1> a(5, aCPP);

index<1> idx(2);

std::cout << a[idx] << "\n";    
// Output: 3  
```  
  
В следующем примере создается двумерный индекс, который указывает элемент, где строки = 1 и столбце = 2 в двухмерный `array_view` объекта. Первый параметр в `index` конструктора — строка, а второй параметр — столбец. Выходные данные — 6.  
  
```cpp  
int aCPP[] = {1, 2, 3, 4, 5, 6};  
array_view<int, 2> a(2, 3, aCPP);  
  
index<2> idx(1, 2);  
  
std::cout <<a[idx] << "\n";    
// Output: 6  
```  
  
В следующем примере создается трехмерный индекс, указывающий элемент где глубина = 0, в строке = 1 и столбце = 3 в трехмерном `array_view` объекта. Обратите внимание на то, что первый параметр — глубина, второй параметр — строка, и третий параметр — столбец. Выходные данные — 8.  
  
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
[Класс extent](../../parallel/amp/reference/extent-class.md) задает длину данных в каждом измерении объекта `array` или `array_view` объекта. Можно создать объект границы и использовать его для создания `array` или `array_view` объекта. Можно также получить границы из существующего `array` или `array_view` объекта. В следующем примере выводится длина границы в каждом измерении объекта `array_view` объекта.  
  
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
  
В следующем примере создается `array_view` объект, который имеет те же измерения как и объект в предыдущем примере, но в этом примере используется `extent` объекта вместо использования явных параметров в `array_view` конструктор.  
  
```cpp  
int aCPP[] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24};  
extent<3> e(2, 3, 4);

array_view<int, 3> a(e, aCPP);

std::cout << "The number of columns is " << a.extent[2] << "\n";  
std::cout << "The number of rows is " << a.extent[1] << "\n";  
std::cout << "The depth is " << a.extent[0] << "\n";  
```  
  
## <a name="moving-data-to-the-accelerator-array-and-arrayview"></a>Перемещение данных на ускоритель: array и array_view  
 
Два контейнера данных, используемый для перемещения данных на ускоритель, определены в библиотеке среды выполнения. Они являются [класс array](../../parallel/amp/reference/array-class.md) и [класс array_view](../../parallel/amp/reference/array-view-class.md). `array` Класса является класс контейнера, который создает глубокую копию данных, при создании объекта. `array_view` Класс является оболочкой для класса, копирует данные, когда функция ядра обращается к данным. Если данные, необходимые на исходном устройстве данные копируются обратно.  
  
### <a name="array-class"></a>Класс array  
Когда `array` объект создан, глубокую копию данных создается на ускорителе, если вы используете конструктор, принимающий указатель на набор данных. Функция ядра изменяет копию на ускорителе. После завершения выполнения функции ядра необходимо скопировать данные обратно к структуре источника данных. Следующий пример умножает каждый элемент в векторе 10. После завершения функции ядра `vector conversion operator` используется для копирования данных обратно в объекте vector.  
  
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
`array_view` Имеет практически те же члены, что `array` класс, но другой основной функциональностью не соответствует. Данные, передаваемые `array_view` конструктор не копируются на графический Процессор, это же касается `array` конструктор. Вместо этого данные копируются в ускоритель при выполнении функции ядра. Таким образом при создании двух `array_view` объектов, которые используют те же данные, оба `array_view` объекты ссылаются на той же области памяти. При этом необходимо синхронизировать любой многопоточный доступ. Основное преимущество использования `array_view` класс является то, что данные перемещаются только в том случае, если это необходимо.  
  
### <a name="comparison-of-array-and-arrayview"></a>Сравнение array и array_view  
В следующей таблице перечислены сходства и различия между `array` и `array_view` классы.  
  
|Описание:|array - класс|array_view - класс|  
|-----------------|-----------------|-----------------------|  
|Определение ранга|Во время компиляции.|Во время компиляции.|  
|Определение границ|Во время выполнения.|Во время выполнения.|  
|Фигура|Прямоугольной.|Прямоугольной.|  
|Хранение данных|— Это контейнер данных.|Является оболочкой данных.|  
|Копировать|Явное глубокое копирование в определение.|Неявное копирование при обращении функцией ядра.|  
|Получение данных|Путем копирования данных массива обратно в объект потока на ЦП.|Прямым обращением `array_view` объекта или путем вызова [метод array_view::synchronize](reference/array-view-class.md#synchronize) для сохраняют доступ к данным в исходном контейнере.|  
  
### <a name="shared-memory-with-array-and-arrayview"></a>Общая память с массивом и array_view  
Общая память — это память, может осуществляться и ЦП, так и сочетания клавиш. Использование общей памяти исключает или значительно снижает нагрузку копирования данных между ЦП и сочетаниями клавиш. Несмотря на то, что память используется совместно, не могут одновременно обращаться центральным Процессором и сочетания клавиш, и благодаря этому приведет к неопределенному поведению.  
  
`array` объекты могут использоваться для указания точного управления использованием общей памяти, если связанный ускоритель его поддерживает. Поддерживает ли ускоритель общей памяти определяется ускорителя [supports_cpu_shared_memory](reference/accelerator-class.md#supports_cpu_shared_memory) свойство, которое возвращает **true** когда общая память поддерживается. Если общая память поддерживается, значение по умолчанию [перечисление access_type](reference/concurrency-namespace-enums-amp.md#access_type) памяти выделения на ускорителе определяется `default_cpu_access_type` свойство. По умолчанию `array` и `array_view` пройти на том же `access_type` что и основной связанный `accelerator`.  
  
Задав [элемент данных array::cpu_access_type](reference/array-class.md#cpu_access_type) свойство `array` явным образом, вы можете более точное управление над об общей памяти используется, таким образом, вы можете оптимизировать приложение для повышения производительности оборудования характеристики на основе шаблонов доступа к памяти его вычислительных ядер. `array_view` Отражает тот же `cpu_access_type` как `array` которой он связан; или, если объект array_view создан без источника данных, его `access_type` отражает среду, которая первой заставляет его выделить память. То есть, если она сначала доступен для узла (ЦП), он ведет себя так, как если бы был создан из источника данных ЦП и общих папок `access_type` из `accelerator_view` связанного захватом; Однако, если это первый обращаться `accelerator_view`, а затем он ведет себя как если бы он был создан для `array` созданном на этом `accelerator_view` и позволяет совместно использовать `array`в `access_type`.  
  
В следующем примере кода показано, как определить, является ли ускоритель по умолчанию поддерживает общей памяти, а затем создает несколько массивов, которые имеют различные конфигурации cpu_access_type.  
  
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
  
## <a name="executing-code-over-data-parallelforeach"></a>Выполнение кода над данными: parallel_for_each  
 
[Parallel_for_each](reference/concurrency-namespace-functions-amp.md#parallel_for_each) функция определяет код, который вы хотите запустить на ускорителе в отношении данных в `array` или `array_view` объекта. Рассмотрим следующий код в начале этого раздела.  
  
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
  
`parallel_for_each` Метод принимает два аргумента, вычислительный домен и лямбда-выражение.  
  
*Вычислительный домен* — `extent` объекта или `tiled_extent` , определяющий набор потоков для параллельного выполнения. Один поток создается для каждого элемента вычислительного домена. В этом случае `extent` объект является одномерным и имеет пять элементов. Таким образом будет запущено пять потоков.  
  
*Лямбда-выражение* определяет код для выполнения в каждом потоке. Предложение отслеживания, `[=]`, указывает, что тело лямбда-выражения осуществляет доступ к всем записанным переменным по значению, которые в данном случае `a`, `b`, и `sum`. В этом примере список параметров создает одномерный массив `index` переменную с именем `idx`. Значение `idx[0]` равно 0 в первом потоке и последовательно увеличивается с каждым следующим потоком. `restrict(amp)` Указывает, что используется только то подмножество языка C++, которого может ускорить C++ AMP.  Ограничения функций, которые имеют модификатор ограничения описаны в [restrict (C++ AMP)](../../cpp/restrict-cpp-amp.md). Дополнительные сведения см. в разделе, [синтаксис лямбда-выражений](../../cpp/lambda-expression-syntax.md).  
  
Лямбда-выражение может включать код, выполняемый, или он может вызывать отдельные функции ядра. Функция ядра должна включать `restrict(amp)` модификатор. Следующий пример эквивалентен предыдущему примеру, но он вызывает отдельные функции ядра.  
  
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
  
## <a name="accelerating-code-tiles-and-barriers"></a>Ускорение кода: Дробление и барьеры  

Можно получить дополнительное ускорение при помощи дробления. Заполнение плитками делит поток на равные прямоугольные подмножества или *плитки*. Можно определить подходящий размер плитки на основе набора данных и алгоритм, который используется для кодирования. Для каждого потока, у вас есть доступ к *глобального* расположение элементов данных относительно целого `array` или `array_view` и доступ к *локального* расположение относительно плитки. Использование локального значения индекса упрощает код, так как не нужно писать код для преобразования глобального значения индекса в локальное. Для использования мозаик необходимо вызвать [метод extent::tile](reference/extent-class.md#tile) в этом вычислительном домене в `parallel_for_each` метод и использование [tiled_index](../../parallel/amp/reference/tiled-index-class.md) объекта в лямбда-выражения.  
  
В типичных приложениях элементы плитки связаны каким-либо образом и код должен получить доступ к и отслеживать значения по всей плитке. Используйте [ключевое слово tile_static](../../cpp/tile-static-keyword.md) ключевое слово и [метод tile_barrier::wait](reference/tile-barrier-class.md#wait) для выполнения этой задачи. Переменную, которая имеет **tile_static** ключевое слово имеет область действия по всей мозаике и экземпляр переменной создается для каждого элемента мозаики. Необходимо обрабатывать синхронизацию доступа потока плитки к переменной. [Метод tile_barrier::wait](reference/tile-barrier-class.md#wait) останавливает выполнение текущего потока, пока все потоки в плитке достигнут вызова `tile_barrier::wait`. Поэтому можно накапливать значения по всей плитке с помощью **tile_static** переменных. Затем можно завершить все вычисления, требующие доступа ко всем значениям.  
  
Следующая схема представляет двухмерный массив данных выборки, осуществленной в мозаиках.  
  
![Индексировать значения в разбитом на плитки](../../parallel/amp/media/camptiledgridexample.png "camptiledgridexample")  
  
В следующем примере кода использует данные выборки из предыдущей схемы. Код заменяет каждое значение в мозаике средним значением всех значений мозаики.  
  
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
 
C++ AMP включает в себя две математические библиотеки. Библиотека двойной точности в [пространство имен Concurrency::precise_math](../../parallel/amp/reference/concurrency-precise-math-namespace.md) обеспечивает поддержку функций двойной точности. Он также предоставляет поддержку для функций одиночной точности, несмотря на то, что по-прежнему необходима поддержка двойной точности на оборудовании. Он соответствует [спецификации C99 (ISO/IEC 9899)](http://go.microsoft.com/fwlink/p/?linkid=225887). Ускоритель должен полностью поддерживать двойную точность. Можно определить путем проверки значения [элемент данных accelerator::supports_double_precision](reference/accelerator-class.md#supports_double_precision). Быстрая математическая библиотека в [пространство имен Concurrency::fast_math](../../parallel/amp/reference/concurrency-fast-math-namespace.md), содержит другой набор математических функций. Эти функции, которые поддерживают только `float` операндов, выполняются быстрее, но не с такой точностью, что и в библиотеке математики двойной точности. Функции содержатся в \<amp_math.h > файл заголовка и все объявлены с `restrict(amp)`. Функции в \<cmath > импортированы в файле заголовка `fast_math` и `precise_math` пространства имен. **Ограничить** ключевое слово используется для различения \<cmath > версию и C++ AMP. В следующем коде вычисляется логарифм по основанию 10, используя быстрый метод для каждого значения, которое находится в домене вычислений.  

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
 
C++ AMP включает в себя графическую библиотеку, которая предназначена для программирования ускоренной графики. Эта библиотека используется только на устройствах, которые поддерживают базовую графическую функциональность. Методы находятся в [пространство имен Concurrency::graphics](../../parallel/amp/reference/concurrency-graphics-namespace.md) и содержатся в \<amp_graphics.h > файл заголовка. Ниже перечислены ключевые компоненты графической библиотеки.  
  
- [Класс Texture](../../parallel/amp/reference/texture-class.md): класс текстуры можно использовать для создания текстуры из памяти или из файла. Текстуры похожи на массивы, поскольку они содержат данные, и они напоминают контейнеры в стандартной библиотеке C++ с точки зрения присваивания и копирования. Дополнительные сведения см. в разделе [Контейнеры стандартной библиотеки C++](../../standard-library/stl-containers.md). Параметры шаблона для `texture` классе: тип элемента и ранг. Ранг может быть 1, 2 или 3. Тип элемента может быть одним из коротких векторных типов, описанных далее в этой статье.  
  
- [Класс writeonly_texture_view](../../parallel/amp/reference/writeonly-texture-view-class.md): обеспечивает доступ к любой текстуре только для записи.  
  
- [Короткий вектор библиотеки](http://msdn.microsoft.com/en-us/4c4f5bed-c396-493b-a238-c347563f645f): Определяет набор коротких векторных типов длиной 2, 3 и 4, которые основаны на **int**, `uint`, **float**, **двойные**, [norm](../../parallel/amp/reference/norm-class.md), или [unorm](../../parallel/amp/reference/unorm-class.md).  
  
## <a name="universal-windows-platform-uwp-apps"></a>Windows универсальных приложений платформы (UWP)  
 
Как и другие библиотеки C++ можно использовать C++ AMP в приложениях UWP. В этих статьях описываются способы включить код C++ AMP в приложениях, созданный с помощью C++, C#, Visual Basic или JavaScript:  
  
- [Использование C++ AMP в приложениях UWP](../../parallel/amp/using-cpp-amp-in-windows-store-apps.md)  
  
- [Пошаговое руководство: Создание базового компонента среды выполнения Windows на C++ и вызов его из JavaScript](http://go.microsoft.com/fwlink/p/?linkid=249077)  
  
- [Bing Maps Trip Optimizer в приложение Store окно в JavaScript и C++](http://go.microsoft.com/fwlink/p/?linkid=249078)  
  
- [Как использовать C++ AMP из C# с помощью среды выполнения Windows](http://go.microsoft.com/fwlink/p/?linkid=249080)  
  
- [Как использовать C++ AMP из C#](http://go.microsoft.com/fwlink/p/?linkid=249081)  
  
- [Вызов неуправляемых функций из управляемого кода](../../dotnet/calling-native-functions-from-managed-code.md)  
  
## <a name="c-amp-and-concurrency-visualizer"></a>C++ AMP и визуализатор параллелизма  
 
Визуализатор параллелизма включает в себя поддержку анализа производительности кода C++ AMP. Эти функции описаны в следующих статьях:  
  
- [Граф активности GPU](/visualstudio/profiling/gpu-activity-graph)  
  
- [Активность GPU (подкачка)](/visualstudio/profiling/gpu-activity-paging)  
  
- [Активность GPU (этот процесс)](/visualstudio/profiling/gpu-activity-this-process)  
  
- [Активность GPU (другие процессы)](/visualstudio/profiling/gpu-activity-other-processes)  
  
- [Каналы (представление "Потоки")](/visualstudio/profiling/channels-threads-view)  
  
- [Анализ кода C++ AMP с Визуализатором параллелизма](http://go.microsoft.com/fwlink/p/?linkid=253987&clcid=0x409)  
  
## <a name="performance-recommendations"></a>Рекомендации по производительности  
 
Получение модуля и деление целых чисел без знака иметь значительно лучшую производительность, чем получение модуля и деление целых чисел со знаком. Мы рекомендуем использовать целые числа без знака по возможности.  
  
## <a name="see-also"></a>См. также  
 
[C++ AMP (C++ Accelerated Massive Parallelism)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)   
[Синтаксис лямбда-выражений](../../cpp/lambda-expression-syntax.md)   
[Справочник (C++ AMP)](../../parallel/amp/reference/reference-cpp-amp.md)   
[Параллельное программирование в блоге машинного кода](http://go.microsoft.com/fwlink/p/?linkid=238472)