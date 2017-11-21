---
title: "Функции &lt;set&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- set/std::swap (map)
- set/std::swap (multiset)
ms.assetid: d1277d14-8502-46c0-b820-bcda820f9406
caps.latest.revision: "7"
manager: ghogen
ms.openlocfilehash: 5580030a16953fbfb3759c955555b646ff1cb15d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="ltsetgt-functions"></a>Функции &lt;set&gt;
|||  
|-|-|  
|[swap (map)](#swap)|[swap (multiset)](#swap_multiset)|  
  
##  <a name="swap"></a>  swap  (map)
 Обмен элементами между двумя наборами.  
  
```
template <class Key, class Traits, class Allocator>  
void swap(set<Key, Traits, Allocator>& left, set<Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Параметры  
 `right`  
 Набор, предоставляющий элементы для обмена местами, или набор, элементы которого должны быть заменены элементами набора `left`.  
  
 `left`  
 Набор, элементы которого должны быть заменены элементами списка `right`.  
  
### <a name="remarks"></a>Примечания  
 Функция-шаблон является специальным алгоритмом, специализированным на классе контейнера, который настроен выполнять функцию-член `left.`[swap](../standard-library/set-class.md#swap)( `right`). Это экземпляр частичного упорядочивания шаблонов функций компилятором. Когда функции-шаблоны перегружаются таким образом, что соответствие шаблона и вызова функции не является уникальным, компилятор выберет наиболее специализированную версию функции-шаблона. Общая версия функции-шаблона  
  
 `template` \< **classT**> **void swap**( **T&**, **T&**)  
  
 в классе алгоритма работает путем назначения и является медленной операцией. Специализированная версия в каждом контейнере работает гораздо быстрее, так как она может работать с внутренним представлением класса контейнера.  
  
### <a name="example"></a>Пример  
  См. пример кода для класса-члена [set::swap](../standard-library/set-class.md#swap), в котором используется версия шаблона `swap`.  
  
##  <a name="swap_multiset"></a>  swap  (multiset)
 Меняет местами элементы двух мультинаборов.  
  
```
template <class Key, class Traits, class Allocator>  
void swap(multiset<Key, Traits, Allocator>& left, multiset<Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Параметры  
 `right`  
 Мультинабор, предоставляющий элементы для обмена, или мультинабор, элементы которого должны быть заменены элементами мультинабора `left`.  
  
 `left`  
 Мультинабор, элементы которого должны быть заменены элементами мультинабора `right`.  
  
### <a name="remarks"></a>Примечания  
 Функция-шаблон является алгоритмом, специализированном на мультинаборе класса контейнеров для выполнения функции-члена `left.`[swap](../standard-library/multiset-class.md#swap)( `right`). Это экземпляр частичного упорядочивания шаблонов функций компилятором. Когда функции-шаблоны перегружаются таким образом, что соответствие шаблона и вызова функции не является уникальным, компилятор выберет наиболее специализированную версию функции-шаблона. Общая версия функции-шаблона  
  
 `template` \< **classT**> **void swap**( **T&**, **T&**)  
  
 в классе алгоритма работает путем назначения и является медленной операцией. Специализированная версия в каждом контейнере работает гораздо быстрее, так как она может работать с внутренним представлением класса контейнера.  
  
### <a name="example"></a>Пример  
  См. пример кода для класса-члена [multiset::swap](../standard-library/multiset-class.md#swap), в котором используется версия шаблона `swap`.  
  
## <a name="see-also"></a>См. также  
 [\<set>](../standard-library/set.md)



