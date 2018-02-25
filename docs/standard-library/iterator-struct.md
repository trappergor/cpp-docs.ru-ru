---
title: "Структура iterator | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- xutility/std::iterator
dev_langs:
- C++
helpviewer_keywords:
- iterator class
- iterator struct
ms.assetid: c74c8000-8b18-4829-9b71-6103c4229b74
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 274d472e3f3768a67a49ed6ca074f3a126bfd0fd
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="iterator-struct"></a>Структура iterator
Пустая базовая структура, используемая для обеспечения правильной работы определяемого пользователем класса итератора с **iterator_trait**.  
  
## <a name="syntax"></a>Синтаксис  
```    
struct iterator {
   typedef Category iterator_category;
   typedef Type value_type;
   typedef Distance difference_type;
   typedef Distance distance_type;
   typedef Pointer pointer;
   typedef Reference reference;
   };  
```    
## <a name="remarks"></a>Примечания  
 Данная структура-шаблон используется как базовый тип для всех итераторов. Она определяет типы членов  
  
- `iterator_category` (синоним для параметра-шаблона `Category`).  
  
- `value_type` (синоним для параметра-шаблона **Type**).  
  
- `difference_type` (синоним для параметра-шаблона `Distance`).  
  
- `distance_type` (синоним для параметра-шаблона `Distance`)  
  
- `pointer` (синоним для параметра-шаблона `Pointer`).  
  
- `reference` (синоним для параметра-шаблона `Reference`).  
  
 Обратите внимание, что `value_type` не должен быть типом константы, даже если **указатель** указывает на объект **типа** const и ссылка обозначает объект **типа** const.  
  
## <a name="example"></a>Пример  
 См. раздел [iterator_traits](../standard-library/iterator-traits-struct.md) с примером того, как объявить и использовать типы в базовом классе итератора.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<iterator>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [\<iterator>](../standard-library/iterator.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)



