---
title: Справочник по библиотеке STL/CLR | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- STL/CLR Library
- STL/CLR, redistribution
- cliext directory
ms.assetid: a9d9ca00-7bf2-48c1-b205-3ae6f8c25f82
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 78dc5c57ca000dfa03dba640c46cec16aaca133f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46429479"
---
# <a name="stlclr-library-reference"></a>Справочник по библиотеке STL/CLR

Библиотека STL/CLR представляет собой упаковки из поднабора стандартной библиотеки C++ для использования с C++ и .NET Framework common language runtime (CLR). С помощью STL/CLR можно использовать все контейнеры, итераторы и алгоритмы стандартной библиотеки в управляемой среде.

Использование STL/CLR:

- Включить заголовки из **cliext** подкаталог вместо обычных эквиваленты стандартной библиотеки C++.

- Уточните имена библиотек с `cliext::` вместо `std::`.

STL/CLR предоставляет универсальные типы и интерфейсы, используемые в сценариях между сборки .NET в сборке **Microsoft.VisualC.STLCLR.dll**. Эта библиотека DLL включена в .NET Framework 3.5. При распространении приложения, которое использует STL/CLR, необходимо включить .NET Framework 3.5, а также других библиотек Visual C++, используемые в проекте, в разделе зависимостей проекта установки.

## <a name="in-this-section"></a>В этом разделе

[Пространство имен cliext](../dotnet/cliext-namespace.md)<br/>
Описание пространства имен, которая содержит все типы библиотеки STL/CLR.

[Контейнеры STL/CLR](../dotnet/stl-clr-containers.md)<br/>
Предоставляет общие сведения о контейнерах, найденные в стандартной библиотеке C++, включая требования к элементам контейнера, типы элементов, которые могут быть вставлены и проблемы владения.

[Требования к элементам контейнера STL/CLR](../dotnet/requirements-for-stl-clr-container-elements.md)<br/>
Описание минимальных требований для всех ссылочных типов, которые вставляются в контейнеры стандартной библиотеки C++.

[Практическое руководство. Преобразование из коллекции .NET в контейнер STL/CLR](../dotnet/how-to-convert-from-a-dotnet-collection-to-a-stl-clr-container.md)<br/>
Описание порядка преобразования коллекции .NET в контейнер STL/CLR.

[Практическое руководство. Преобразование из контейнера STL/CLR в коллекцию .NET](../dotnet/how-to-convert-from-a-stl-clr-container-to-a-dotnet-collection.md)<br/>
Описание порядка преобразования контейнера STL/CLR в коллекцию .NET.

[Практическое руководство. Предоставление контейнера STL/CLR из сборки](../dotnet/how-to-expose-an-stl-clr-container-from-an-assembly.md)<br/>
Показано, как отобразить элементы нескольких контейнеров STL/CLR, записанных в сборке на C++.

Кроме того в этом разделе также описаны следующие компоненты STL/CLR:

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