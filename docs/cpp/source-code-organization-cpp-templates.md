---
title: Организация исходного кода (шаблоны C++)
ms.date: 04/22/2019
ms.assetid: 50569c5d-0219-4966-9bcf-a8689074ad1d
ms.openlocfilehash: ecd682056f27200ae31c27295c1aabaf72c74a18
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87186117"
---
# <a name="source-code-organization-c-templates"></a>Организация исходного кода (шаблоны C++)

При определении шаблона класса необходимо организовать исходный код таким образом, чтобы определения элементов были видны компилятору, когда они ему нужны. Вы можете выбрать *модель включения* или модель *явного создания экземпляра*. В модели включения определения элементов включаются в каждый файл, использующий шаблон. Это самый простой подход. Он обеспечивает максимальную гибкость с точки зрения того, какие конкретные типы могут использоваться в шаблоне. Его недостаток в том, что он может увеличивать время компиляции. Воздействие может быть значительным, если проект или сами включенные файлы имеют большой размер. В рамках подхода явного создания экземпляров сам шаблон создает экземпляры конкретных классов или элементов класса для определенных типов.  Этот подход может уменьшить время компиляции, но он ограничивает использование только теми классами, которые разработчик шаблона включил заранее. Как правило, модель включения рекомендуется использовать, если время компиляции не является проблемой.

## <a name="background"></a>Историческая справка

Шаблоны не похожи на обычные классы в том смысле, что компилятор не создает объектный код для шаблона или любого из его элементов. Ничего не создается, пока экземпляр шаблона не будет создан с конкретными типами. Когда компилятор обнаруживает создание экземпляра шаблона, такого как `MyClass<int> mc;`, и класс с такой сигнатурой еще не существует, он создает такой класс. Он также пытается создать код для любых используемых функций-элементов. Если эти определения находятся в файле, который прямо или косвенно не включен (#include) в СРР-файл, который компилируется, компилятор не сможет их увидеть.  С точки зрения компилятора, это не обязательно ошибка, потому что функции могут быть определены в другой записи преобразования, и в этом случае компоновщик найдет их.  Если компоновщик не находит этот код, он создает *неразрешенную внешнюю* ошибку.

## <a name="the-inclusion-model"></a>Модель включения

Самый простой и наиболее распространенный способ сделать определения шаблонов видимыми во всей записи преобразования — это поместить определения в сам файл заголовка.  Любой CPP-файл, который использует шаблон, должен включать в себя (#include) заголовок. Этот подход используется в стандартной библиотеке.

```cpp
#ifndef MYARRAY
#define MYARRAY
#include <iostream>

template<typename T, size_t N>
class MyArray
{
    T arr[N];
public:
    // Full definitions:
    MyArray(){}
    void Print()
    {
        for (const auto v : arr)
        {
            std::cout << v << " , ";
        }
    }

    T& operator[](int i)
   {
       return arr[i];
   }
};
#endif
```

При таком подходе компилятор имеет доступ к полному определению шаблона и может создавать экземпляры шаблонов по запросу для любого типа. Он прост и достаточно легкий в плане обслуживания. Тем не менее модель включения затратнее с точки зрения времени компиляции. Эти затраты могут возрасти в крупных программах, особенно если сам заголовок шаблона содержит (#include) другие заголовки. Каждый *`.cpp`* файл, #includes заголовок, получает собственную копию шаблонов функций и всех определений. Обычно компоновщик сможет разобраться в ситуации, чтобы у вас не было нескольких определений для функции, но для этого потребуется время. В случае небольших программ дополнительное время компиляции будет существенно меньше.

## <a name="the-explicit-instantiation-model"></a>Модель явного создания экземпляра

Если модель включения не подходит для проекта и вы точно понимаете набор типов, которые будут использоваться для создания экземпляра шаблона, можно разделить код шаблона на *`.h`* файл и и *`.cpp`* в *`.cpp`* файле явным образом создать экземпляры шаблонов. Это приведет к созданию объектного кода, который компилятор распознает при обработке пользовательских экземпляров.

Чтобы явно создать экземпляр, используйте шаблон ключевого слова, за которым следует сигнатура сущности, которую вы хотите создать. Это может быть тип или элемент. Если вы явно создаете экземпляр типа, будут созданы все элементы.

```cpp
template MyArray<double, 5>;
```

```cpp
//MyArray.h
#ifndef MYARRAY
#define MYARRAY

template<typename T, size_t N>
class MyArray
{
    T arr[N];
public:
    MyArray();
    void Print();
    T& operator[](int i);
};
#endif

//MyArray.cpp
#include <iostream>
#include "MyArray.h"

using namespace std;

template<typename T, size_t N>
MyArray<T,N>::MyArray(){}

template<typename T, size_t N>
void MyArray<T,N>::Print()
{
    for (const auto v : arr)
    {
        cout << v << "'";
    }
    cout << endl;
}

template MyArray<double, 5>;template MyArray<string, 5>;
```

В предыдущем примере явные экземпляры находятся в нижней части CPP-файла. `MyArray`Может использоваться только для **`double`** `String` типов или.

> [!NOTE]
> В C++ 11 **`export`** ключевое слово было объявлено устаревшим в контексте определений шаблонов. На практике это мало что дает, потому что большинство компиляторов никогда его не поддерживали.
