---
title: "range_adapter (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::range_adapter
dev_langs: C++
helpviewer_keywords: range_adapter class [STL/CLR]
ms.assetid: 3fbe2a65-1216-46a0-a182-422816b80cfb
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5455c1912b3108291f530ee9488a4e0078ba39a2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="rangeadapter-stlclr"></a>range_adapter (STL/CLR)
Класс шаблона, который создает оболочку для пары итераторы, которые позволяют реализовать несколько интерфейсов в библиотеке базовых классов (BCL). Range_adapter позволяет управлять диапазон STL/CLR, как если бы оно коллекции BCL.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<typename Iter>  
    ref class range_adapter  
        :   public  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<Value>,  
        System::Collections::Generic::ICollection<Value>  
    { ..... };  
```  
  
#### <a name="parameters"></a>Параметры  
 Iter  
 Тип, связанный с упакованного итераторов.  
  
## <a name="members"></a>Члены  
  
|Функция-член|Описание|  
|---------------------|-----------------|  
|[range_adapter::range_adapter (STL/CLR)](../dotnet/range-adapter-range-adapter-stl-clr.md)|Создает объект адаптера.|  
  
|Оператор|Описание|  
|--------------|-----------------|  
|[range_adapter::operator= (STL/CLR)](../dotnet/range-adapter-operator-assign-stl-clr.md)|Заменяет сохраненный итератор пары.|  
  
## <a name="interfaces"></a>Интерфейсы  
  
|Интерфейс|Описание|  
|---------------|-----------------|  
|<xref:System.Collections.IEnumerable>|Перебор элементов в коллекции.|  
|<xref:System.Collections.ICollection>|Поддерживает группу элементов.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Перебор типизированных элементов в коллекции...|  
|<xref:System.Collections.Generic.ICollection%601>|Поддерживает группу типизированных элементов.|  
  
## <a name="remarks"></a>Примечания  
 Range_adapter сохраняет пару итераторов, которые в свою очередь разделения последовательность элементов. Объект реализует четыре BCL интерфейсы, которые позволяют выполнять итерацию по элементам в порядке. Используйте этот класс шаблона для работы с STL/CLR диапазоны как контейнеры BCL.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext адаптер >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [collection_adapter (STL/CLR)](../dotnet/collection-adapter-stl-clr.md)   
 [make_collection (STL/CLR)](../dotnet/make-collection-stl-clr.md)