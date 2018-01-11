---
title: "Класс value_compare (&lt;map&gt;) | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std::value_compare
- std.value_compare
- map/std::value_compare
- value_compare
dev_langs: C++
helpviewer_keywords: std::value_compare
ms.assetid: ea97c1d0-04b2-4d42-8d96-23522c04cc41
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1e05f4e0f4431ac9911f98c10540b7aa03a3f486
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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
  См. пример объявления и использования `value_compare` в примере для [value_comp](../standard-library/map-class.md#value_comp).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<map>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [Структура binary_function](../standard-library/binary-function-struct.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)



