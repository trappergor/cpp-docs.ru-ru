---
title: "Требования к элементам контейнера STL/CLR | Документы Microsoft"
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
- C++ Standard Library, template class containers
- STL/CLR, containers
- containers, STL/CLR
- containers, C++ Standard Library
ms.assetid: 59ab240c-15bf-4701-a9f9-e7c56e5ab53f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 3317e3c9349963fc24b37b421def05c475732fd8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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