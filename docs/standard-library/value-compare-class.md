---
title: "Класс value_compare | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: value_compare
dev_langs: C++
helpviewer_keywords: value_compare class
ms.assetid: c306c5b9-3505-4357-aa6b-216451b951ed
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a340acbc50c629686f010f51ce07e397e4084154
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="valuecompare-class"></a>Класс value_compare
Предоставляет объект функции, который может сравнивать элементы hash_map путем сравнения значения ключей для определения относительного порядка в hash_map.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class value_compare
 : std::public binary_function<value_type, value_type, bool>
{
public:
    bool operator()(
    const value_type& left,
    const value_type& right) const
 {
    return (comp(left.first, right.first));

 }
protected:
    value_compare(const key_compare& c) : comp (c) { }
    key_compare comp;
};
```  
  
## <a name="remarks"></a>Примечания  
 Критерии сравнения, предоставляемые сравнением значений между **типами_значений** всех элементов, содержащихся в объекте hash_map, вытекают из сравнения между ключами соответствующих элементов во вспомогательном классе. Оператор функции-члена использует объект **comp** типа `key_compare`, который хранится в объекте функции, предоставляемом value_compare, для сравнения ключей сортировки компонентов для двух элементов.  
  
 Для объектов hash_set и hash_multiset, которые представляют собой простые контейнеры, в которых значения ключей идентичны значениям элементов, value_compare эквивалентно `key_compare`; для объектов hash_map и hash_multimap это не так, так как элементы типа `pair` не эквивалентны значению ключа элемента.  
  
   
  
## <a name="example"></a>Пример  
 Пример определения и использования value_compare см. в разделе [hash_map::value_comp](../standard-library/hash-map-class.md#value_comp).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<hash_map>  
  
 **Пространство имен:** stdext  
  
## <a name="see-also"></a>См. также  
 [Структура binary_function](../standard-library/binary-function-struct.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)



