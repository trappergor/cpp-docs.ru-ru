---
title: "Управляемые типы (C++ CL) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- __gc types
- types [C++], CLR
ms.assetid: 1ddd114e-be02-4de7-a4dd-a2d72ad8ff81
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 058c2c2c2c8c54a0c4c7d290326c4af453c73d05
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="managed-types-ccl"></a>Управляемые типы (C++/CL)
Синтаксис для объявления управляемых типов, а также создания и использования объектов этих типов значительно изменен с управляемых расширений для C++ к Visual C++. Это было сделано для обеспечения их интеграции в рамках системы типов ISO C++. В следующих подразделах подробно представлены эти изменения.  
  
## <a name="in-this-section"></a>Содержание  
 [Объявление управляемых типов классов](../dotnet/declaration-of-a-managed-class-type.md)  
 Описывает, как объявлять управляемый `class`, `struct`, или `interface`.  
  
 [Объявление объекта ссылочного класса в среде CLR](../dotnet/declaration-of-a-clr-reference-class-object.md)  
 В этой статье описывается объявление объекта ссылочного типа класса с помощью дескриптора отслеживания.  
  
 [Объявление массива CLR](../dotnet/declaration-of-a-clr-array.md)  
 Объясняет, как объявить и инициализировать массив.  
  
 [Изменения в последовательности инициализации конструктора](../dotnet/changes-in-constructor-initialization-order.md)  
 Рассматриваются основные изменения в последовательности инициализации конструктора класса.  
  
 [Изменения в семантике деструктора](../dotnet/changes-in-destructor-semantics.md)  
 Рассматривается неопределенное завершение `Finalize` и `Dispose`, влияние на ссылаться на объекты, а также использование явного `Finalize`.  
  
 **Примечание:** обсуждение делегатов откладывается до [делегатов и событий](../dotnet/delegates-and-events.md) для представления их с членами события внутри класса, общий раздел [объявления членов в пределах класса или интерфейса (C + +/ CLI) ](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md).  
  
## <a name="see-also"></a>См. также  
 [C + +/ CLI Основы миграции](../dotnet/cpp-cli-migration-primer.md)   
 [Классы и структуры](../windows/classes-and-structs-cpp-component-extensions.md)   
 [Массивы](../windows/arrays-cpp-component-extensions.md)