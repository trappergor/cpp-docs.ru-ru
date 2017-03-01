---
title: "Класс value_compare (&lt;map&gt;) | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std::value_compare
- std.value_compare
- map/std::value_compare
- value_compare
dev_langs:
- C++
helpviewer_keywords:
- value_compare class
ms.assetid: ea97c1d0-04b2-4d42-8d96-23522c04cc41
caps.latest.revision: 21
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
ms.openlocfilehash: 200e62472c8c6002cdc45181ad019a1d78ca7977
ms.lasthandoff: 02/24/2017

---
# <a name="valuecompare-class-ltmapgt"></a>Класс value_compare (&lt;map&gt;)
Предоставляет объект функции, который может сравнить элементы объекта map, сравнивая значения их ключей, чтобы определить их относительный порядок в объекте map.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class value_compare : public binary_function<value_type, value_type, bool>
{
public:
    bool operator()(const value_type& left, const value_type& right) const;
    value_compare(key_compare pred) : comp(pred);
protected:
    key_compare comp;
};
```  
  
## <a name="remarks"></a>Примечания  
 Критерий сравнения, предоставляемый `value_compare`, между **типами_значений** всех элементов, содержащихся в сопоставлении, вытекает из сравнения между ключами соответствующих элементов во вспомогательном классе. Оператор функции-члена использует объект **comp** типа `key_compare`, который хранится в объекте функции, предоставляемом `value_compare`, для сравнения ключей сортировки компонентов для двух элементов.  
  
 Для наборов и множественных наборов, которые представляют собой простые контейнеры, в которых значения ключей идентичны значениям элементов, `value_compare` эквивалентно `key_compare`; для сопоставлений и объектов multimap, это не так, так как элементы типа `pair` не эквивалентны значению ключа элемента.  
  
## <a name="example"></a>Пример  
  См. пример объявления и использования `value_compare` в примере для [value_comp](../standard-library/map-class.md#map__value_comp).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<map>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [Структура binary_function](../standard-library/binary-function-struct.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)




