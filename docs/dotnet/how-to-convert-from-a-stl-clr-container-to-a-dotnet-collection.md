---
title: Практическое руководство. Преобразование из контейнера STL/CLR в коллекцию .NET
ms.date: 11/04/2016
helpviewer_keywords:
- STL/CLR Containers [STL/CLR]
- STL/CLR, converting to .NET collections
ms.assetid: 70b2dfd9-869c-4e0f-9a29-b1ee0cb0d107
ms.openlocfilehash: cf67e362751dd164916cc94cd644d55110d88a5f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387530"
---
# <a name="how-to-convert-from-a-stlclr-container-to-a-net-collection"></a>Практическое руководство. Преобразование из контейнера STL/CLR в коллекцию .NET

В этом разделе показано, как преобразовать контейнеры STL/CLR в их эквивалент коллекций .NET. В качестве примера мы покажем, как преобразовать STL/CLR [вектор](../dotnet/vector-stl-clr.md) к типу .NET <xref:System.Collections.Generic.ICollection%601> и как преобразовать STL/CLR [карты](../dotnet/map-stl-clr.md) к типу .NET <xref:System.Collections.Generic.IDictionary%602>, но процедура одинакова для всех коллекций и контейнеры.

### <a name="to-create-a-collection-from-a-container"></a>Создание коллекции из контейнера

1. Используйте один из следующих методов:

   - Чтобы преобразовать часть контейнера, вызовите [make_collection](../dotnet/make-collection-stl-clr.md) функции и передать итератору begin и конечный итератор контейнера STL/CLR, необходимо скопировать в коллекции .NET. Эта функция шаблона принимает итератор STL/CLR в качестве аргумента шаблона. В первом примере этот метод.

   - Для преобразования всего контейнера, приведите контейнера в соответствующий интерфейс коллекции .NET или интерфейса коллекции. Второй пример демонстрирует этот метод.

## <a name="example"></a>Пример

В этом примере мы создаем STL/CLR `vector` и добавьте в него 5 элементами. Затем создаем коллекции .NET путем вызова `make_collection` функции. Наконец мы отображаем содержимое вновь созданной коллекции.

```
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

В этом примере мы создаем STL/CLR `map` и добавьте в него 5 элементами. Затем создаем .NET <xref:System.Collections.Generic.IDictionary%602> и назначить `map` непосредственно к нему. Наконец мы отображаем содержимое вновь созданной коллекции.

```
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

## <a name="see-also"></a>См. также

[Справочник по библиотеке STL/CLR](../dotnet/stl-clr-library-reference.md)<br/>
[Практическое руководство. Преобразование из коллекции .NET в контейнер STL/CLR](../dotnet/how-to-convert-from-a-dotnet-collection-to-a-stl-clr-container.md)<br/>
[range_adapter (STL/CLR)](../dotnet/range-adapter-stl-clr.md)
