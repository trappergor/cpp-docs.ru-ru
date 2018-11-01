---
title: Требования к элементам контейнера STL/CLR
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- C++ Standard Library, template class containers
- STL/CLR, containers
- containers, STL/CLR
- containers, C++ Standard Library
ms.assetid: 59ab240c-15bf-4701-a9f9-e7c56e5ab53f
ms.openlocfilehash: 0744d38a08dbd972b786e1cc74c112322ecf181f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50428578"
---
# <a name="requirements-for-stlclr-container-elements"></a>Требования к элементам контейнера STL/CLR

Все ссылочные типы, которые вставляются в контейнеры STL/CLR требуется как минимум, следующие элементы:

- Открытый конструктор копий.

- Оператор присваивания открытого.

- Открытый деструктор.

Кроме того ассоциативных контейнеров, таких как [задать](../dotnet/set-stl-clr.md) и [карты](../dotnet/map-stl-clr.md) должен иметь открытый оператор сравнения, который является `operator<` по умолчанию. Открытый конструктор по умолчанию и открытый оператор равенства должна определяться может потребовать некоторых операций в контейнерах.

Как ссылочные типы, типы значений и дескрипторов для ссылки на типы, которые должны быть вставлены в ассоциативный контейнер должен иметь такие как оператор сравнения `operator<` определен. Требования к открытый конструктор копий, оператор присваивания открытый и открытого деструктора не существуют для типов значений или маркеры для ссылки на типы.

## <a name="see-also"></a>См. также

[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)