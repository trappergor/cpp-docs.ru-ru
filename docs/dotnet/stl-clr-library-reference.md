---
title: Справочник по библиотеке STL/CLR
ms.date: 09/18/2018
ms.topic: reference
helpviewer_keywords:
- STL/CLR Library
- STL/CLR, redistribution
- cliext directory
ms.assetid: a9d9ca00-7bf2-48c1-b205-3ae6f8c25f82
ms.openlocfilehash: e6804dab814eca4ecc5fd23c74cbbb21eac3be77
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88839703"
---
# <a name="stlclr-library-reference"></a>Справочник по библиотеке STL/CLR

Библиотека STL/CLR предоставляет интерфейс, аналогичный контейнерам стандартной библиотеки C++ для использования с C++ и .NET Framework среде CLR. STL/CLR полностью отделен от реализации Майкрософт стандартной библиотеки C++. STL/CLR поддерживается для устаревшей поддержки, но не актуальна в стандарте C++. При возможности настоятельно рекомендуется использовать собственные контейнеры [стандартной библиотеки C++](../standard-library/cpp-standard-library-reference.md) вместо STL/CLR.

Для использования STL/CLR:

- Включите заголовки из подкаталога **cliext** include вместо обычной стандартной библиотеки C++.

- Уточните имена библиотек с помощью `cliext::` вместо `std::` .

Библиотека STL/CLR предоставляет интерфейс, подобный STL, для использования с C++ и .NET Framework среды CLR. Эта библиотека поддерживается для устаревшей поддержки, но не актуальна в стандарте C++. Настоятельно рекомендуется использовать собственные контейнеры [стандартной библиотеки C++](../standard-library/cpp-standard-library-reference.md) вместо STL/CLR.

## <a name="in-this-section"></a>в этом разделе

[Пространство имен cliext](../dotnet/cliext-namespace.md)<br/>
Описывает пространство имен, которое содержит все типы библиотеки STL/CLR.

[Контейнеры STL/CLR](../dotnet/stl-clr-containers.md)<br/>
Содержит общие сведения о контейнерах, которые находятся в стандартной библиотеке C++, включая требования для элементов контейнера, типы элементов, которые могут быть вставлены, и проблемы владения.

[Требования для элементов контейнера STL/CLR](../dotnet/requirements-for-stl-clr-container-elements.md)<br/>
Описывает минимальные требования для всех ссылочных типов, которые вставляются в контейнеры стандартной библиотеки C++.

[Как преобразовать коллекцию .NET в контейнер STL/CLR](../dotnet/how-to-convert-from-a-dotnet-collection-to-a-stl-clr-container.md)<br/>
Описывает, как преобразовать коллекцию .NET в контейнер STL/CLR.

[Как преобразовать контейнер STL/CLR в коллекцию .NET](../dotnet/how-to-convert-from-a-stl-clr-container-to-a-dotnet-collection.md)<br/>
Описывает, как преобразовать контейнер STL/CLR в коллекцию .NET.

[Как предоставить контейнер STL/CLR из сборки](../dotnet/how-to-expose-an-stl-clr-container-from-an-assembly.md)<br/>
Показывает, как отобразить элементы нескольких контейнеров STL/CLR, написанных в сборке C++.

Кроме того, в этом разделе описаны следующие компоненты STL/CLR:

:::row:::
   :::column span="":::
      [`adapter` (STL/CLR)](../dotnet/adapter-stl-clr.md)\
      [`algorithm` (STL/CLR)](../dotnet/algorithm-stl-clr.md)\
      [`deque` (STL/CLR)](../dotnet/deque-stl-clr.md)\
      [`for each`, `in`](../dotnet/for-each-in.md)\
      [`functional` (STL/CLR)](../dotnet/functional-stl-clr.md)\
      [`hash_map` (STL/CLR)](../dotnet/hash-map-stl-clr.md)\
      [`hash_multimap` (STL/CLR)](../dotnet/hash-multimap-stl-clr.md)\
      [`hash_multiset` (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)\
      [`hash_set` (STL/CLR)](../dotnet/hash-set-stl-clr.md)\
      [`list` (STL/CLR)](../dotnet/list-stl-clr.md)\
   :::column-end:::
   :::column span="":::
      [`map` (STL/CLR)](../dotnet/map-stl-clr.md)\
      [`multimap` (STL/CLR)](../dotnet/multimap-stl-clr.md)\
      [`multiset` (STL/CLR)](../dotnet/multiset-stl-clr.md)\
      [`numeric` (STL/CLR)](../dotnet/numeric-stl-clr.md)\
      [`priority_queue` (STL/CLR)](../dotnet/priority-queue-stl-clr.md)\
      [`queue` (STL/CLR)](../dotnet/queue-stl-clr.md)\
      [`set` (STL/CLR)](../dotnet/set-stl-clr.md)\
      [`stack` (STL/CLR)](../dotnet/stack-stl-clr.md)\
      [`utility` (STL/CLR)](../dotnet/utility-stl-clr.md)\
      [`vector` (STL/CLR)](../dotnet/vector-stl-clr.md)\
   :::column-end:::
:::row-end:::

## <a name="see-also"></a>См. также раздел

[Стандартная библиотека C++](../standard-library/cpp-standard-library-reference.md)
