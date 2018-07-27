---
title: 'Как: преобразование из контейнера STL/CLR в коллекцию .NET | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- STL/CLR Containers [STL/CLR]
- STL/CLR, converting to .NET collections
ms.assetid: 70b2dfd9-869c-4e0f-9a29-b1ee0cb0d107
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 7fb4938121d1d2beed3133bee6013e17d37f1402
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33132012"
---
# <a name="how-to-convert-from-a-stlclr-container-to-a-net-collection"></a>Практическое руководство. Преобразование из контейнера STL/CLR в коллекцию .NET
В этом разделе показано, как преобразовать контейнеры STL/CLR в эквивалентные в коллекциях .NET. В качестве примера мы показывают, как преобразовать STL/CLR [вектор](../dotnet/vector-stl-clr.md) для .NET <xref:System.Collections.Generic.ICollection%601> и преобразование STL/CLR [карты](../dotnet/map-stl-clr.md) для .NET <xref:System.Collections.Generic.IDictionary%602>, но процедура одинакова для всех коллекций и контейнеры.  
  
### <a name="to-create-a-collection-from-a-container"></a>Чтобы создать коллекцию из контейнера  
  
1.  Используйте один из следующих методов:  
  
    -   Чтобы преобразовать частью контейнера, вызовите [make_collection](../dotnet/make-collection-stl-clr.md) функцией и передать begin итератора и итератора после конца контейнера STL/CLR, необходимо скопировать в коллекции .NET. Эта функция шаблона принимает итератор STL/CLR в качестве аргумента шаблона. В первом примере этот метод.  
  
    -   Для преобразования всего контейнера, приведите контейнера, соответствующий интерфейс коллекции .NET или коллекцию интерфейса. Во втором примере демонстрируется этот метод.  
  
## <a name="example"></a>Пример  
 В этом примере мы создадим STL/CLR `vector` и добавьте в нее 5 элементов. Затем мы создайте коллекцию .NET путем вызова `make_collection` функции. Наконец мы можем отобразить содержимое созданную коллекцию.  
  
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
 В этом примере мы создадим STL/CLR `map` и добавьте в нее 5 элементов. Затем мы создаем .NET <xref:System.Collections.Generic.IDictionary%602> и назначить `map` непосредственно к ней. Наконец мы можем отобразить содержимое созданную коллекцию.  
  
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
 [Справочник по библиотеке STL/CLR](../dotnet/stl-clr-library-reference.md)   
 [Как: преобразование из коллекции .NET в контейнер STL/CLR](../dotnet/how-to-convert-from-a-dotnet-collection-to-a-stl-clr-container.md)   
 [range_adapter (STL/CLR)](../dotnet/range-adapter-stl-clr.md)