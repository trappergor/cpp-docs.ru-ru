---
title: "Практическое руководство. Преобразование из коллекции .NET в контейнер STL/CLR | Microsoft Docs"
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
  - "STL/CLR, преобразование из коллекций .NET"
ms.assetid: bb927c48-78e8-4150-bd0b-787c651f4a87
caps.latest.revision: 9
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Преобразование из коллекции .NET в контейнер STL/CLR
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В этом разделе показано, как преобразовать коллекции .NET в их соответствующим контейнерам STL\/CLR.  В качестве примера на экране отображается, как преобразовать .NET <xref:System.Collections.Generic.List%601> в STL\/CLR [vector](../dotnet/vector-stl-clr.md) и преобразовании .NET <xref:System.Collections.Generic.Dictionary%602> в STL\/CLR [КАРТА](../dotnet/map-stl-clr.md), но процедура подобна для всех коллекций и контейнеров.  
  
### Создание контейнера из коллекции  
  
1.  Для преобразования всей коллекции создайте контейнер STL\/CLR и передайте коллекцию в конструктор.  
  
     Первый пример демонстрирует эту процедуру.  
  
 — или —  
  
1.  Создание контейнера универсальный шаблон STL\/CLR путем создания объекта [collection\_adapter](../Topic/collection_adapter%20\(STL-CLR\).md).  Этот класс шаблона принимает интерфейс коллекции .NET в качестве аргумента.  Для проверки поддерживаются интерфейсов см. в разделе [collection\_adapter](../Topic/collection_adapter%20\(STL-CLR\).md).  
  
2.  Скопируйте содержимое коллекции .NET в контейнер.  Это можно сделать с помощью STL\/CLR [алгоритм](../Topic/algorithm%20\(STL-CLR\).md) или путем перебор коллекции .NET и вставки копию каждого элемента в контейнер STL\/CLR.  
  
     Второй пример демонстрирует эту процедуру.  
  
## Пример  
 В этом примере мы создадим универсальный шаблон <xref:System.Collections.Generic.List%601> и добавить в него 5 элементов.  Затем мы создадим `vector` с использованием конструктора, принимающего <xref:System.Collections.Generic.IEnumerable%601> в качестве аргумента.  
  
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
  
  **Содержимое cliext::vector:**  
**2**  
**3**  
**5**  
**7**  
**11**   
## Пример  
 В этом примере мы создадим универсальный шаблон <xref:System.Collections.Generic.Dictionary%602> и добавить в него 5 элементов.  Затем мы создадим `collection_adapter` для создания <xref:System.Collections.Generic.Dictionary%602> как простой контейнер STL\/CLR.  Наконец, мы создаем `map` и копируем содержимое <xref:System.Collections.Generic.Dictionary%602> в `map`, перебор `collection_adapter`.  Во время этого процесса мы создадим новую пару с помощью функции `make_pair` и вводим новые пары непосредственно в `map`.  
  
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
  
  **Содержимое cliext::map:**  
**Key: 0.00 Value: 0**  
**Key: 13.00 Value: 13**  
**Key: 22.00 Value: 22**  
**Key: 42.00 Value: 42**  
**Key: 74.00 Value: 74**   
## См. также  
 [Библиотека STL\/CLR](../dotnet/stl-clr-library-reference.md)   
 [adapter](../dotnet/adapter-stl-clr.md)   
 [Практическое руководство. Преобразование из контейнера STL\/CLR в коллекцию .NET](../dotnet/how-to-convert-from-a-stl-clr-container-to-a-dotnet-collection.md)