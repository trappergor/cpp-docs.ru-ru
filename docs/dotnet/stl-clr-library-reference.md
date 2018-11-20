---
title: Справочник по библиотеке STL/CLR
ms.date: 09/18/2018"
ms.topic: reference
helpviewer_keywords:
- STL/CLR Library
- STL/CLR, redistribution
- cliext directory
ms.assetid: a9d9ca00-7bf2-48c1-b205-3ae6f8c25f82
ms.openlocfilehash: 6914b61597e38c94a214089ecc3aeed17aec46d3
ms.sourcegitcommit: 984fb4814a2dd9bcea5ec88c9528707f17a7cffa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2018
ms.locfileid: "51949522"
---
# <a name="stlclr-library-reference"></a>Справочник по библиотеке STL/CLR

Библиотека STL/CLR предоставляет интерфейсом, похожим на контейнеры стандартной библиотеки C++ для использования с C++ и .NET Framework common language runtime (CLR). STL/CLR никак не связано с реализацией стандартной библиотеки C++. STL/CLR, сохранено для поддержки прежних версий, но не обновляются стандарту C++. Мы настоятельно рекомендуем использовать собственные [стандартной библиотеки C++](../standard-library/cpp-standard-library-reference.md) контейнеров вместо STL/CLR, когда это возможно.

Использование STL/CLR:

- Включить заголовки из **cliext** подкаталог вместо обычных эквиваленты стандартной библиотеки C++.

- Уточните имена библиотек с `cliext::` вместо `std::`.

Библиотека STL/CLR предоставляет интерфейс наподобие STL для использования с C++ и .NET Framework common language runtime (CLR). Эта библиотека, сохранено для поддержки прежних версий, но не обновляются стандарту C++. Мы настоятельно рекомендуем использовать собственные [стандартной библиотеки C++](../standard-library/cpp-standard-library-reference.md) контейнеров вместо STL/CLR.

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
