---
title: "Справочник по библиотеке STL/CLR | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cliext - каталог"
  - "Библиотека STL/CLR"
  - "STL/CLR, распространение"
ms.assetid: a9d9ca00-7bf2-48c1-b205-3ae6f8c25f82
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# Справочник по библиотеке STL/CLR
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Библиотека STL\/CLR, которая представляет собой упакованную библиотеку стандартных шаблонов \(STL\), входящую в состав стандартной библиотеки C\+\+, предназначенной для использования в C\+\+ и среде CLR платформы .NET Framework.  При помощи библиотеки STL\/CLR можно использовать все контейнеры, итераторы и алгоритмы библиотеки STL в управляемой среде.  
  
 Для использования STL\/CLR выполните следующие действия:  
  
-   Включить заголовки из **cliext** в подкаталог вместо обычных стандартных эквивалентов библиотеки времени выполнения C\+\+.  
  
-   Уточните имена библиотек с `cliext::` вместо `std::`.  
  
 STL\/CLR предоставляет универсальные типы и интерфейсы, которые она использует в сценариях между сборки .NET в сборке **Microsoft.VisualC.STLCLR.dll**.  Эта библиотека DLL включена в платформу .NET Framework 3.5.  При распространении приложения, которое использует STL\/CLR потребуется включить платформы .NET Framework 3.5, а также все остальные библиотеки Visual C\+\+ в проекте используется в разделе зависимостей проекта установки.  
  
## В этом подразделе  
 [Пространство имен cliext](../Topic/cliext%20Namespace.md)  
 Описание пространства имен, содержащего все типы библиотеки STL\/CLR.  
  
 [Контейнеры STL\/CLR](../dotnet/stl-clr-containers.md)  
 Общие сведения о контейнерах, найденные в стандартной библиотеке C\+\+, в том числе требования для элементов\-контейнеров, типов элементов, которые могут добавляться, и проблемы владения.  
  
 [Требования к элементам контейнера STL\/CLR](../Topic/Requirements%20for%20STL-CLR%20Container%20Elements.md)  
 Описание минимальных требований для всех ссылочных типов, которые вставляются в контейнеры STL.  
  
 [Практическое руководство. Преобразование из коллекции .NET в контейнер STL\/CLR](../dotnet/how-to-convert-from-a-dotnet-collection-to-a-stl-clr-container.md)  
 Описание порядка преобразования коллекции .NET в контейнер STL\/CLR.  
  
 [Практическое руководство. Преобразование из контейнера STL\/CLR в коллекцию .NET](../dotnet/how-to-convert-from-a-stl-clr-container-to-a-dotnet-collection.md)  
 Описание порядка преобразования контейнера STL\/CLR в коллекцию коллекции .NET.  
  
 [Практическое руководство. Предоставление контейнера STL\/CLR из сборки](../dotnet/how-to-expose-an-stl-clr-container-from-an-assembly.md)  
 Показано, как отобразить элементы нескольких контейнеров STL\/CLR, написанных в сборке на C\+\+.  
  
 Кроме того, в этом разделе также описаны следующие компоненты STL\/CLR:  
  
|||  
|-|-|  
|[adapter](../dotnet/adapter-stl-clr.md)|[algorithm](../Topic/algorithm%20\(STL-CLR\).md)|  
|[deque](../dotnet/deque-stl-clr.md)|[for each, in](../dotnet/for-each-in.md)|  
|[functional](../dotnet/functional-stl-clr.md)|[hash\_map](../dotnet/hash-map-stl-clr.md)|  
|[hash\_multimap](../dotnet/hash-multimap-stl-clr.md)|[hash\_multiset](../dotnet/hash-multiset-stl-clr.md)|  
|[hash\_set](../dotnet/hash-set-stl-clr.md)|[list](../dotnet/list-stl-clr.md)|  
|[map](../dotnet/map-stl-clr.md)|[multimap](../dotnet/multimap-stl-clr.md)|  
|[multiset](../dotnet/multiset-stl-clr.md)|[числовой](../dotnet/numeric-stl-clr.md)|  
|[priority\_queue](../Topic/priority_queue%20\(STL-CLR\).md)|[queue](../Topic/queue%20\(STL-CLR\).md)|  
|[набор](../dotnet/set-stl-clr.md)|[стек](../dotnet/stack-stl-clr.md)|  
|[utility](../dotnet/utility-stl-clr.md)|[вектор](../dotnet/vector-stl-clr.md)|  
  
## См. также  
 [Стандартная библиотека C\+\+](../standard-library/cpp-standard-library-reference.md)