---
title: "Функции &lt;map&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7cb3d1a5-7add-4726-a73f-61927eafd466
caps.latest.revision: 6
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 85c900f2263ae1c1089478badc85388e3b5e8548
ms.openlocfilehash: d322b318ac4206c5bc27b81299190d129548ef9f
ms.lasthandoff: 02/24/2017

---
# <a name="ltmapgt-functions"></a>Функции &lt;map&gt;
|||  
|-|-|  
|[swap (map)](#swap)|[swap (multimap)](#swap_multimap)|  
  
##  <a name="a-nameswapmultimapa--swap--map"></a><a name="swap_multimap"></a>  swap  (map)
 Обмен элементами между двумя сопоставлениями.  
  
```  
template <class key, class T, class _Pr, class _Alloc>  
void swap(
    map<Key, Traits, Compare, Alloctor>& left,  
    map<Key, Traits, Compare, Alloctor>& right);
```  
  
### <a name="parameters"></a>Параметры  
 ` right`  
 Сопоставление, предоставляющее элементы для обмена местами, или сопоставление, элементы которого должны быть заменены на элементы сопоставления ` left`.  
  
 ` left`  
 Сопоставление, элементы которого должны быть заменены на элементы сопоставления ` right`.  
  
### <a name="remarks"></a>Примечания  
 Функция-шаблон является алгоритмом, специализированным на сопоставлении класса контейнера для выполнения функции-члена ` left.`[swap](../standard-library/map-class.md#map__swap)*(right*). Это экземпляр частичного упорядочивания шаблонов функций компилятором. Когда функции-шаблоны перегружаются таким образом, что соответствие шаблона и вызова функции не является уникальным, компилятор выберет наиболее специализированную версию функции-шаблона. Общая версия функции-шаблона, **template** \< **class T**> **void swap**(**T&**, **T&**) в классе алгоритма работает с помощью назначения и выполняется медленно. Специализированная версия в каждом контейнере работает гораздо быстрее, так как она может работать с внутренним представлением класса контейнера.  
  
### <a name="example"></a>Пример  
  См. пример кода для функции-члена [map::swap](../standard-library/map-class.md#map__swap), в котором используется версия шаблона `swap`.  
  
##  <a name="a-nameswapa--swap--multimap"></a><a name="swap"></a>  swap  (multimap)
 Обмен элементами между двумя multimap.  
  
```  
template <class key, class T, class _Pr, class _Alloc>  
void swap(
    multimap<Key, Traits, Compare, Alloctor>& left,  
    multimap<Key, Traits, Compare, Alloctor>& right);
```  
  
### <a name="parameters"></a>Параметры  
 ` right`  
 Multimap, предоставляющий элементы для обмена местами, или multimap, элементы которого должны быть заменены на элементы multimap ` left`.  
  
 ` left`  
 Multimap, элементы которого должны быть заменены на элементы multimap ` right`.  
  
### <a name="remarks"></a>Примечания  
 Функция-шаблон является алгоритмом, специализированным на сопоставлении класса контейнера для выполнения multimap класса контейнера функции-члена ` left.`[swap](../standard-library/multimap-class.md#multimap__swap) (` right`). Это экземпляр частичного упорядочивания шаблонов функций компилятором. Когда функции-шаблоны перегружаются таким образом, что соответствие шаблона и вызова функции не является уникальным, компилятор выберет наиболее специализированную версию функции-шаблона. Общая версия функции-шаблона, **template** \< **class T**> **void swap**(**T&**, **T&**) в классе алгоритма работает с помощью назначения и выполняется медленно. Специализированная версия в каждом контейнере работает гораздо быстрее, так как она может работать с внутренним представлением класса контейнера.  
  
### <a name="example"></a>Пример  
  См. пример кода для функции-члена [multimap::swap](../standard-library/multimap-class.md#multimap__swap), в котором используется версия шаблона `swap`.  
  
## <a name="see-also"></a>См. также  
 [\<map>](../standard-library/map.md)

