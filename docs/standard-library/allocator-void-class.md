---
title: "Класс allocator&lt;void&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- memory/std::allocator<void>
- allocator<void>
dev_langs:
- C++
helpviewer_keywords:
- allocator<void> class
ms.assetid: abfb40f5-c600-46a6-b130-f42c6535b2bd
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cef6f292938ea503ec50fd72e6b7a710d9a40951
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
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



