---
title: "Справочник по библиотеке STL/CLR | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- STL/CLR Library
- STL/CLR, redistribution
- cliext directory
ms.assetid: a9d9ca00-7bf2-48c1-b205-3ae6f8c25f82
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: aecb7c509fc1b072086a8772c3430c43b67350be
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="stlclr-library-reference"></a>Справочник по библиотеке STL/CLR
Библиотека STL/CLR представляет собой упакованную подмножества стандартной библиотеки C++ для использования с C++ и .NET Framework common language runtime (CLR). С помощью STL/CLR можно использовать все контейнеры, итераторов и алгоритмов стандартной библиотеки в управляемой среде.  
  
 Чтобы использовать STL/CLR:  
  
-   Включить заголовки из **cliext** включают подкаталог вместо обычного эквивалентов стандартной библиотеки C++.  
  
-   Квалифицировать имена библиотек с `cliext::` вместо `std::`.  
  
 STL/CLR предоставляет универсальные типы и интерфейсы, используемые в сценариях между сборками в сборке .NET **Microsoft.VisualC.STLCLR.dll**. Эта библиотека DLL входит в .NET Framework 3.5. При распространении приложения, использующего STL/CLR необходимо включить .NET Framework 3.5, а также других библиотек Visual C++, используемых проектом, в разделе зависимости проекта установки.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Пространство имен cliext](../dotnet/cliext-namespace.md)  
 Описывает пространство имен, которое содержит все типы из библиотеки STL/CLR.  
  
 [Контейнеры STL/CLR](../dotnet/stl-clr-containers.md)  
 Обзор контейнеров, которые находятся в стандартной библиотеке C++, включая требования к элементам контейнера, типы элементов, которые могут быть вставлены и проблемы владения.  
  
 [Требования к элементам контейнера STL/CLR](../dotnet/requirements-for-stl-clr-container-elements.md)  
 Описывает минимальные требования для всех ссылочных типов, которые будут вставляться в контейнеры стандартной библиотеки C++.  
  
 [Практическое руководство. Преобразование из коллекции .NET в контейнер STL/CLR](../dotnet/how-to-convert-from-a-dotnet-collection-to-a-stl-clr-container.md)  
 Описывает, как для преобразования коллекции .NET в контейнер STL/CLR.  
  
 [Практическое руководство. Преобразование из контейнера STL/CLR в коллекцию .NET](../dotnet/how-to-convert-from-a-stl-clr-container-to-a-dotnet-collection.md)  
 Описывает преобразование контейнера STL/CLR в коллекцию .NET.  
  
 [Практическое руководство. Предоставление контейнера STL/CLR из сборки](../dotnet/how-to-expose-an-stl-clr-container-from-an-assembly.md)  
 Показывает порядок отображения элементов несколько контейнеров STL/CLR, записанных в сборке C++.  
  
 Кроме того в этом разделе также описываются следующие компоненты STL/CLR:  
  
|||  
|-|-|  
|[adapter (STL/CLR)](../dotnet/adapter-stl-clr.md)|[algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)|  
|[deque (STL/CLR)](../dotnet/deque-stl-clr.md)|[for each, in](../dotnet/for-each-in.md)|  
|[functional (STL/CLR)](../dotnet/functional-stl-clr.md)|[hash_map (STL/CLR)](../dotnet/hash-map-stl-clr.md)|  
|[hash_multimap (STL/CLR)](../dotnet/hash-multimap-stl-clr.md)|[hash_multiset (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)|  
|[hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)|[list (STL/CLR)](../dotnet/list-stl-clr.md)|  
|[map (STL/CLR)](../dotnet/map-stl-clr.md)|[multimap (STL/CLR)](../dotnet/multimap-stl-clr.md)|  
|[multiset (STL/CLR)](../dotnet/multiset-stl-clr.md)|[numeric (STL/CLR)](../dotnet/numeric-stl-clr.md)|  
|[priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)|[queue (STL/CLR)](../dotnet/queue-stl-clr.md)|  
|[set (STL/CLR)](../dotnet/set-stl-clr.md)|[stack (STL/CLR)](../dotnet/stack-stl-clr.md)|  
|[utility (STL/CLR)](../dotnet/utility-stl-clr.md)|[vector (STL/CLR)](../dotnet/vector-stl-clr.md)|  
  
## <a name="see-also"></a>См. также  
 [Стандартная библиотека C++](../standard-library/cpp-standard-library-reference.md)