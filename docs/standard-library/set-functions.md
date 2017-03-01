---
title: "Функции &lt;set&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d1277d14-8502-46c0-b820-bcda820f9406
caps.latest.revision: 7
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: fb2b30dc58b7ba65dd13a07cec8456ea4adeb5e1
ms.lasthandoff: 02/24/2017

---
# <a name="ltsetgt-functions"></a>Функции &lt;set&gt;
|||  
|-|-|  
|[swap (map)](#swap)|[swap (multiset)](#swap_multiset)|  
  
##  <a name="a-nameswapa--swap--map"></a><a name="swap"></a>  swap  (map)
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
 Функция-шаблон является специальным алгоритмом, специализированным на классе контейнера, который настроен выполнять функцию-член `left``.`[swap](../standard-library/set-class.md#set__swap)( `right`). Это экземпляр частичного упорядочивания шаблонов функций компилятором. Когда функции-шаблоны перегружаются таким образом, что соответствие шаблона и вызова функции не является уникальным, компилятор выберет наиболее специализированную версию функции-шаблона. Общая версия функции-шаблона  
  
 `template` \< **classT**> **void swap**( **T&**, **T&**)  
  
 в классе алгоритма работает путем назначения и является медленной операцией. Специализированная версия в каждом контейнере работает гораздо быстрее, так как она может работать с внутренним представлением класса контейнера.  
  
### <a name="example"></a>Пример  
  См. пример кода для класса-члена [set::swap](../standard-library/set-class.md#set__swap), в котором используется версия шаблона `swap`.  
  
##  <a name="a-nameswapmultiseta--swap--multiset"></a><a name="swap_multiset"></a>  swap  (multiset)
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
 Функция-шаблон является алгоритмом, специализированном на мультинаборе класса контейнеров для выполнения функции-члена `left``.`[swap](../standard-library/multiset-class.md#multiset__swap)( `right`). Это экземпляр частичного упорядочивания шаблонов функций компилятором. Когда функции-шаблоны перегружаются таким образом, что соответствие шаблона и вызова функции не является уникальным, компилятор выберет наиболее специализированную версию функции-шаблона. Общая версия функции-шаблона  
  
 `template` \< **classT**> **void swap**( **T&**, **T&**)  
  
 в классе алгоритма работает путем назначения и является медленной операцией. Специализированная версия в каждом контейнере работает гораздо быстрее, так как она может работать с внутренним представлением класса контейнера.  
  
### <a name="example"></a>Пример  
  См. пример кода для класса-члена [multiset::swap](../standard-library/multiset-class.md#multiset__swap), в котором используется версия шаблона `swap`.  
  
## <a name="see-also"></a>См. также  
 [\<set>](../standard-library/set.md)




