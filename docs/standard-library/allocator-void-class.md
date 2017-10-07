---
title: "Класс allocator&lt;void&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- memory/std::allocator<void>
- allocator<void>
dev_langs:
- C++
helpviewer_keywords:
- allocator<void> class
ms.assetid: abfb40f5-c600-46a6-b130-f42c6535b2bd
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: d816804e15e7a02edbe07f131529bf719039459f
ms.contentlocale: ru-ru
ms.lasthandoff: 10/03/2017

---
# <a name="allocatorltvoidgt-class"></a>Класс allocator&lt;void&gt;
Специализация класса шаблона allocator для типа `void`, определяющая типы, имеющие смысл в данном контексте.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <>
class allocator<void> {
    typedef void *pointer;
    typedef const void *const_pointer;
    typedef void value_type;
    template <class Other>
    struct rebind;
    allocator();
    allocator(const allocator<void>&);

    template <class Other>
    allocator(const allocator<Other>&);

    template <class Other>
    allocator<void>& operator=(const allocator<Other>&);
};
```  
  
## <a name="remarks"></a>Примечания  
 Этот класс явно специализирует класс шаблона [allocator](../standard-library/allocator-class.md) для типа *void.* Его конструкторы и оператор присваивания ведут себя так же, как для класса шаблона, но он определяет только следующие типы:  
  
- [const_pointer](../standard-library/allocator-class.md#const_pointer);  
  
- [pointer](../standard-library/allocator-class.md#pointer);  
  
- [value_type](../standard-library/allocator-class.md#value_type);  
  
- [rebind](../standard-library/allocator-class.md#rebind), вложенный класс шаблона.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<memory>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)




