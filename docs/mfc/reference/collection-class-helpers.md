---
title: "Вспомогательные функции классов коллекции | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros.classes"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "классы коллекций, вспомогательные функции"
  - "ConstructElements - функция"
  - "DestructElements - функция"
  - "класс коллекции функций вспомогательного приложения"
  - "SerializeElements - функция"
ms.assetid: bc3a2368-9edd-4748-9e6a-13cba79517ca
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# Вспомогательные функции классов коллекции
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Классы коллекций `CMap`, `CList` и использование `CArray` атрибутами глобальные вспомогательные функции для этих целей, как сравнение, копирование и издающ сериализацию элементов.  В рамках реализации классов на основе `CMap`, `CList` и `CArray` следует переопределить эти функции по мере необходимости с версии портняжничанные к типу данных, хранящихся на сопоставлении, списке или массиве.  Сведения о переопределении вспомогательные функции, такие как `SerializeElements` см. в статье [Коллекции: Создание типобезопасную коллекцию](../../mfc/how-to-make-a-type-safe-collection.md).  Обратите внимание, что **ConstructElements** и **DestructElements** стали нерекомендуемыми.  
  
 Библиотеки Microsoft Foundation Class предоставляет следующие глобальные функции, позволяющие настраивать классов коллекций.  
  
### Вспомогательных классов коллекций  
  
|||  
|-|-|  
|[CompareElements](../Topic/CompareElements.md)|Указывает, является ли элементы одинаково.|  
|[CopyElements](../Topic/CopyElements.md)|Копирует элементы из одного массива в другой.|  
|[DumpElements](../Topic/DumpElements.md)|Предоставляет ориентированный на поток диагностические данные.|  
|[HashKey](../Topic/HashKey.md)|Вычисляет хэш ключа.|  
|[SerializeElements](../Topic/SerializeElements.md)|Хранит и извлекает элементы на или из архива.|  
  
## См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)   
 [CMap Class](../../mfc/reference/cmap-class.md)   
 [CList Class](../../mfc/reference/clist-class.md)   
 [CArray Class](../../mfc/reference/carray-class.md)