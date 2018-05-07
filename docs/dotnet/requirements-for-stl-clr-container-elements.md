---
title: Требования к элементам контейнера STL/CLR | Документы Microsoft
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
ms.openlocfilehash: 523b3e8d3f9c04a933f37032fcea670d75dafccf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="requirements-for-stlclr-container-elements"></a>Требования к элементам контейнера STL/CLR
Все ссылочные типы, которые будут вставляться в контейнеры STL/CLR требуется как минимум, следующие элементы:  
  
-   Открытый конструктор копий.  
  
-   Оператор присваивания открытый.  
  
-   Открытый деструктор.  
  
 Кроме того ассоциативных контейнеров, таких как [задать](../dotnet/set-stl-clr.md) и [карты](../dotnet/map-stl-clr.md) необходимо определить открытый оператор сравнения, который является `operator<` по умолчанию. Для некоторых операций в контейнерах может также потребоваться открытый конструктор по умолчанию и открытый оператор равенства определен.  
  
 Как ссылочные типы, типы значений и дескрипторов для ссылки на типы, которые должны быть вставлены в ассоциативный контейнер должен иметь такие как оператор сравнения `operator<` определен. Требования к открытый конструктор копий, оператор присваивания открытый и открытого деструктора не существуют для типов значений или маркеры для ссылки на типы.  
  
## <a name="see-also"></a>См. также  
 [Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)