---
title: Практическое руководство. Преобразование из контейнера STL/CLR в коллекцию .NET
ms.date: 11/04/2016
helpviewer_keywords:
- STL/CLR Containers [STL/CLR]
- STL/CLR, converting to .NET collections
ms.assetid: 70b2dfd9-869c-4e0f-9a29-b1ee0cb0d107
ms.openlocfilehash: f7539b10ca6c503aede61d19de3d14fb9dcee8be
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "79545309"
---
# <a name="how-to-convert-from-a-stlclr-container-to-a-net-collection"></a>Практическое руководство. Преобразование из контейнера STL/CLR в коллекцию .NET

В этом разделе показано, как преобразовать контейнеры STL/CLR в эквивалентные коллекции .NET. В качестве примера мы покажем, как преобразовать [вектор](../dotnet/vector-stl-clr.md) STL/clr в <xref:System.Collections.Generic.ICollection%601> .NET и преобразовать [карту](../dotnet/map-stl-clr.md) stl/CLR в <xref:System.Collections.Generic.IDictionary%602>.NET, но процедура аналогична для всех коллекций и контейнеров.

### <a name="to-create-a-collection-from-a-container"></a>Создание коллекции из контейнера

1. Используйте один из следующих методов.

   - Чтобы преобразовать часть контейнера, вызовите функцию [make_collection](../dotnet/make-collection-stl-clr.md) и передайте итератор Begin и End итератора из контейнера STL/CLR в коллекцию .NET. Эта функция шаблона принимает итератор STL/CLR в качестве аргумента шаблона. В первом примере демонстрируется этот метод.

   - Чтобы преобразовать весь контейнер, приведите его к соответствующему интерфейсу коллекции .NET или коллекции интерфейсов. Во втором примере демонстрируется этот метод.

## <a name="example"></a>Пример

В этом примере мы создадим `vector` STL/CLR и добавим в нее 5 элементов. Затем мы создадим коллекцию .NET, вызвав функцию `make_collection`. Наконец, мы отображаем содержимое только что созданной коллекции.

```cpp
// cliext_convert_vector_to_icollection.cpp
// compile with: /clr

#include <cliext/adapter>
#include <cliext/vector>

using namespace cliext;
using namespace System;
using namespace System::Collections::Generic;

int main(array<System::String ^> ^args)
{
    cliext::vector<int> primeNumbersCont;
    primeNumbersCont.push_back(2);
    primeNumbersCont.push_back(3);
    primeNumbersCont.push_back(5);
    primeNumbersCont.push_back(7);
    primeNumbersCont.push_back(11);

    System::Collections::Generic::ICollection<int> ^iColl =
        make_collection<cliext::vector<int>::iterator>(
            primeNumbersCont.begin() + 1,
            primeNumbersCont.end() - 1);

    Console::WriteLine("The contents of the System::Collections::Generic::ICollection are:");
    for each (int i in iColl)
    {
        Console::WriteLine(i);
    }
}
```

```Output
The contents of the System::Collections::Generic::ICollection are:
3
5
7
```

## <a name="example"></a>Пример

В этом примере мы создадим `map` STL/CLR и добавим в нее 5 элементов. Затем мы создадим <xref:System.Collections.Generic.IDictionary%602> .NET и назначайте `map` непосредственно. Наконец, мы отображаем содержимое только что созданной коллекции.

```cpp
// cliext_convert_map_to_idictionary.cpp
// compile with: /clr

#include <cliext/adapter>
#include <cliext/map>

using namespace cliext;
using namespace System;
using namespace System::Collections::Generic;

int main(array<System::String ^> ^args)
{
    cliext::map<float, int> ^aMap = gcnew cliext::map<float, int>;
    aMap->insert(cliext::make_pair<float, int>(42.0, 42));
    aMap->insert(cliext::make_pair<float, int>(13.0, 13));
    aMap->insert(cliext::make_pair<float, int>(74.0, 74));
    aMap->insert(cliext::make_pair<float, int>(22.0, 22));
    aMap->insert(cliext::make_pair<float, int>(0.0, 0));

    System::Collections::Generic::IDictionary<float, int> ^iDict = aMap;

    Console::WriteLine("The contents of the IDictionary are:");
    for each (KeyValuePair<float, int> ^kvp in iDict)
    {
        Console::WriteLine("Key: {0:F} Value: {1}", kvp->Key, kvp->Value);
    }
}
```

```Output
The contents of the IDictionary are:
Key: 0.00 Value: 0
Key: 13.00 Value: 13
Key: 22.00 Value: 22
Key: 42.00 Value: 42
Key: 74.00 Value: 74
```

## <a name="see-also"></a>См. также:

[Справочник по библиотеке STL/CLR](../dotnet/stl-clr-library-reference.md)<br/>
[Практическое руководство. Преобразование из коллекции .NET в контейнер STL/CLR](../dotnet/how-to-convert-from-a-dotnet-collection-to-a-stl-clr-container.md)<br/>
[range_adapter (STL/CLR)](../dotnet/range-adapter-stl-clr.md)
