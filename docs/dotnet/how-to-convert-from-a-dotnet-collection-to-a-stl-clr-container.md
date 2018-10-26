---
title: 'Практическое: преобразование из коллекции .NET в контейнер STL/CLR | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- STL/CLR, converting from .NET collections
- STL/CLR Containers [STL/CLR]
ms.assetid: bb927c48-78e8-4150-bd0b-787c651f4a87
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4dd67728773df86f9961fe54c7dd9e4a08ec743d
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50060953"
---
# <a name="how-to-convert-from-a-net-collection-to-a-stlclr-container"></a>Практическое руководство. Преобразование из коллекции .NET в контейнер STL/CLR

В этом разделе показано, как для преобразования коллекции .NET в их эквивалент контейнеры STL/CLR. В качестве примера мы покажем, как преобразовать .NET <xref:System.Collections.Generic.List%601> для STL/CLR [вектор](../dotnet/vector-stl-clr.md) и как преобразовать .NET <xref:System.Collections.Generic.Dictionary%602> для STL/CLR [карты](../dotnet/map-stl-clr.md), но процедура одинакова для всех коллекций и контейнеров .

### <a name="to-create-a-container-from-a-collection"></a>Чтобы создать контейнер из коллекции

1. Чтобы преобразовать всю коллекцию, создайте контейнер STL/CLR и коллекция передается в конструктор.

   В первом примере показано этой процедуры.

-ИЛИ-

1. Создание универсального контейнера STL/CLR, создав [collection_adapter](../dotnet/collection-adapter-stl-clr.md) объекта. Этот класс шаблона принимает интерфейс коллекции .NET в качестве аргумента. Чтобы проверить, какие интерфейсы поддерживаются, см. в разделе [collection_adapter (STL/CLR)](../dotnet/collection-adapter-stl-clr.md).

1. Скопируйте содержимое коллекции .NET в контейнер. Это можно сделать с помощью STL/CLR [алгоритм](../dotnet/algorithm-stl-clr.md), или путем прохода по коллекции .NET и Вставка копии каждого элемента в контейнер STL/CLR.

   Второй пример демонстрирует эту процедуру.

## <a name="example"></a>Пример

В этом примере мы создадим универсальный <xref:System.Collections.Generic.List%601> и добавьте в него 5 элементами. Затем создаем `vector` с помощью конструктора, принимающего <xref:System.Collections.Generic.IEnumerable%601> как аргумент.

```
// cliext_convert_list_to_vector.cpp
// compile with: /clr

#include <cliext/adapter>
#include <cliext/algorithm>
#include <cliext/vector>

using namespace System;
using namespace System::Collections;
using namespace System::Collections::Generic;

int main(array<System::String ^> ^args)
{
    List<int> ^primeNumbersColl = gcnew List<int>();
    primeNumbersColl->Add(2);
    primeNumbersColl->Add(3);
    primeNumbersColl->Add(5);
    primeNumbersColl->Add(7);
    primeNumbersColl->Add(11);

    cliext::vector<int> ^primeNumbersCont =
        gcnew cliext::vector<int>(primeNumbersColl);

    Console::WriteLine("The contents of the cliext::vector are:");
    cliext::vector<int>::const_iterator it;
    for (it = primeNumbersCont->begin(); it != primeNumbersCont->end(); it++)
    {
        Console::WriteLine(*it);
    }
}
```

```Output
The contents of the cliext::vector are:
2
3
5
7
11
```

## <a name="example"></a>Пример

В этом примере мы создадим универсальный <xref:System.Collections.Generic.Dictionary%602> и добавьте в него 5 элементами. Затем создаем `collection_adapter` программы-оболочки для <xref:System.Collections.Generic.Dictionary%602> как простой контейнер STL/CLR. Наконец, мы создаем `map` и скопируйте содержимое <xref:System.Collections.Generic.Dictionary%602> для `map` перебор `collection_adapter`. В ходе этого процесса мы создадим новую пару, с помощью `make_pair` функции и вставить новую пару непосредственно в `map`.

```
// cliext_convert_dictionary_to_map.cpp
// compile with: /clr

#include <cliext/adapter>
#include <cliext/algorithm>
#include <cliext/map>

using namespace System;
using namespace System::Collections;
using namespace System::Collections::Generic;

int main(array<System::String ^> ^args)
{
    System::Collections::Generic::Dictionary<float, int> ^dict =
        gcnew System::Collections::Generic::Dictionary<float, int>();
    dict->Add(42.0, 42);
    dict->Add(13.0, 13);
    dict->Add(74.0, 74);
    dict->Add(22.0, 22);
    dict->Add(0.0, 0);

    cliext::collection_adapter<System::Collections::Generic::IDictionary<float, int>> dictAdapter(dict);
    cliext::map<float, int> aMap;
    for each (KeyValuePair<float, int> ^kvp in dictAdapter)
    {
        cliext::pair<float, int> aPair = cliext::make_pair(kvp->Key, kvp->Value);
        aMap.insert(aPair);
    }

    Console::WriteLine("The contents of the cliext::map are:");
    cliext::map<float, int>::const_iterator it;
    for (it = aMap.begin(); it != aMap.end(); it++)
    {
        Console::WriteLine("Key: {0:F} Value: {1}", it->first, it->second);
    }
}
```

```Output
The contents of the cliext::map are:
Key: 0.00 Value: 0
Key: 13.00 Value: 13
Key: 22.00 Value: 22
Key: 42.00 Value: 42
Key: 74.00 Value: 74
```

## <a name="see-also"></a>См. также

[Справочник по библиотеке STL/CLR](../dotnet/stl-clr-library-reference.md)<br/>
[adapter (STL/CLR)](../dotnet/adapter-stl-clr.md)<br/>
[Практическое руководство. Преобразование из контейнера STL/CLR в коллекцию .NET](../dotnet/how-to-convert-from-a-stl-clr-container-to-a-dotnet-collection.md)