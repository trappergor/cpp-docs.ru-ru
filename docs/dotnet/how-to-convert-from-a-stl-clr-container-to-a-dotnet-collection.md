---
title: "Практическое руководство. Преобразование из контейнера STL/CLR в коллекцию .NET | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "STL/CLR - контейнеры [STL/CLR]"
  - "STL/CLR, преобразование в коллекции .NET"
ms.assetid: 70b2dfd9-869c-4e0f-9a29-b1ee0cb0d107
caps.latest.revision: 8
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Преобразование из контейнера STL/CLR в коллекцию .NET
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В этом разделе показано, как преобразовать контейнеры STL\/CLR их соответствующим коллекциям .NET.  Например, на экране отображается, как преобразовать STL\/CLR [vector](../dotnet/vector-stl-clr.md) в .NET <xref:System.Collections.Generic.ICollection%601> и преобразовании STL\/CLR [КАРТА](../dotnet/map-stl-clr.md) в .NET <xref:System.Collections.Generic.IDictionary%602>, но процедура подобна для всех коллекций и контейнеров.  
  
### Создание коллекции из контейнера  
  
1.  Используйте один из следующих методов:  
  
    -   Преобразовать часть контейнера, необходимо вызвать функцию [make\_collection](../dotnet/make-collection-stl-clr.md), и передать итератор разработки и итератор конца контейнера STL\/CLR, которое должно быть скопировано в коллекцию .NET.  Эта итератор STL\/CLR шаблонная функция принимает в качестве аргумента шаблона.  Первый пример демонстрирует этот метод.  
  
    -   Чтобы преобразовать весь контейнер, преобразуйте контейнер в соответствующие интерфейс коллекции .NET или коллекции интерфейса.  Второй пример демонстрирует этот метод.  
  
## Пример  
 В этом примере мы создадим STL\/CLR `vector` и добавить в него 5 элементов.  Затем мы создадим коллекция .NET путем вызова функции `make_collection`.  Наконец, на экране отображается содержимое вновь созданной коллекции.  
  
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
  
  **Содержимое System::Collections::Generic::ICollection:**  
**3**  
**5**  
**7**   
## Пример  
 В этом примере мы создадим STL\/CLR `map` и добавить в него 5 элементов.  Затем мы создадим .NET <xref:System.Collections.Generic.IDictionary%602> и присвоим `map` непосредственно на него.  Наконец, на экране отображается содержимое вновь созданной коллекции.  
  
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
  
  **Содержимое IDictionary:**  
**Key: 0.00 Value: 0**  
**Key: 13.00 Value: 13**  
**Key: 22.00 Value: 22**  
**Key: 42.00 Value: 42**  
**Key: 74.00 Value: 74**   
## См. также  
 [Библиотека STL\/CLR](../dotnet/stl-clr-library-reference.md)   
 [Практическое руководство. Преобразование из коллекции .NET в контейнер STL\/CLR](../dotnet/how-to-convert-from-a-dotnet-collection-to-a-stl-clr-container.md)   
 [range\_adapter](../dotnet/range-adapter-stl-clr.md)