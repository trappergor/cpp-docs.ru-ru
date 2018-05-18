---
title: Управляемые типы (C++ CL) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- __gc types
- types [C++], CLR
ms.assetid: 1ddd114e-be02-4de7-a4dd-a2d72ad8ff81
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 42426c45f4b8caf3cd4cb61ee867470dc9ea639f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="managed-types-ccl"></a>Управляемые типы (C++/CL)
Синтаксис для объявления управляемых типов, а также создания и использования объектов этих типов значительно изменен с управляемых расширений для C++ к Visual C++. Это было сделано для обеспечения их интеграции в рамках системы типов ISO C++. В следующих подразделах подробно представлены эти изменения.  
  
## <a name="in-this-section"></a>В этом разделе  
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