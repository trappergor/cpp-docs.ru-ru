---
title: "Структура iterator | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- iterator
- std::iterator
- std.iterator
- xutility/std::iterator
dev_langs:
- C++
helpviewer_keywords:
- iterator class
- iterator struct
ms.assetid: c74c8000-8b18-4829-9b71-6103c4229b74
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 2d05749ba2837a3879c91886b9266de47dd2ece6
ms.openlocfilehash: b14712f36d8cc7b4dbbdd4fd6a0cef3cb0667d8b
ms.lasthandoff: 02/24/2017

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




