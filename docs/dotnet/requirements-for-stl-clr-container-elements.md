---
title: Требования к элементам контейнера STL/CLR | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- C++ Standard Library, template class containers
- STL/CLR, containers
- containers, STL/CLR
- containers, C++ Standard Library
ms.assetid: 59ab240c-15bf-4701-a9f9-e7c56e5ab53f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: fcba36fdf280cef31efb9a84288475fcbb82b291
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46400431"
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