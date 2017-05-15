---
title: "Функции &lt;map&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- map/std::swap (map)
- map/std::swap (multimap)
ms.assetid: 7cb3d1a5-7add-4726-a73f-61927eafd466
caps.latest.revision: 6
manager: ghogen
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: a72fb2cd6a34cc7946503593657aa0c3a5dc894e
ms.contentlocale: ru-ru
ms.lasthandoff: 04/29/2017

---
# <a name="ltmapgt-functions"></a>Функции &lt;map&gt;
|||  
|-|-|  
|[swap (map)](#swap)|[swap (multimap)](#swap_multimap)|  
  
##  <a name="swap_multimap"></a>  swap  (map)
 Обмен элементами между двумя сопоставлениями.  
  
```  
template <class key, class T, class _Pr, class _Alloc>  
void swap(
    map<Key, Traits, Compare, Alloctor>& left,  
    map<Key, Traits, Compare, Alloctor>& right);
```  
  
### <a name="parameters"></a>Параметры  
 `right`  
 Сопоставление, предоставляющее элементы для обмена местами, или сопоставление, элементы которого должны быть заменены на элементы сопоставления `left`.  
  
 `left`  
 Сопоставление, элементы которого должны быть заменены на элементы сопоставления `right`.  
  
### <a name="remarks"></a>Примечания  
 Функция шаблона является алгоритмом, который специализируется на карте класс контейнера, чтобы выполнить функцию-член `left`.[ swap](../standard-library/map-class.md#swap)( `right`). Это экземпляр частичного упорядочивания шаблонов функций компилятором. Когда функции-шаблоны перегружаются таким образом, что соответствие шаблона и вызова функции не является уникальным, компилятор выберет наиболее специализированную версию функции-шаблона. Общая версия функции-шаблона, **template** \< **class T**> **void swap**(**T&**, **T&**) в классе алгоритма работает с помощью назначения и выполняется медленно. Специализированная версия в каждом контейнере работает гораздо быстрее, так как она может работать с внутренним представлением класса контейнера.  
  
### <a name="example"></a>Пример  
  См. пример кода для функции-члена [map::swap](../standard-library/map-class.md#swap), в котором используется версия шаблона `swap`.  
  
##  <a name="swap"></a>  swap  (multimap)
 Обмен элементами между двумя multimap.  
  
```  
template <class key, class T, class _Pr, class _Alloc>  
void swap(
    multimap<Key, Traits, Compare, Alloctor>& left,  
    multimap<Key, Traits, Compare, Alloctor>& right);
```  
  
### <a name="parameters"></a>Параметры  
 `right`  
 Multimap, предоставляющий элементы для обмена местами, или multimap, элементы которого должны быть заменены на элементы multimap `left`.  
  
 `left`  
 Multimap, элементы которого должны быть заменены на элементы multimap `right`.  
  
### <a name="remarks"></a>Примечания  
 Функция шаблона является алгоритмом, который специализируется на карте класс контейнера для выполнения на несколько карт класс контейнера для выполнения функции-члена `left`.[ swap](../standard-library/multimap-class.md#swap) ( `right`). Это экземпляр частичного упорядочивания шаблонов функций компилятором. Когда функции-шаблоны перегружаются таким образом, что соответствие шаблона и вызова функции не является уникальным, компилятор выберет наиболее специализированную версию функции-шаблона. Общая версия функции-шаблона, **template** \< **class T**> **void swap**(**T&**, **T&**) в классе алгоритма работает с помощью назначения и выполняется медленно. Специализированная версия в каждом контейнере работает гораздо быстрее, так как она может работать с внутренним представлением класса контейнера.  
  
### <a name="example"></a>Пример  
  См. пример кода для функции-члена [multimap::swap](../standard-library/multimap-class.md#swap), в котором используется версия шаблона `swap`.  
  
## <a name="see-also"></a>См. также  
 [\<map>](../standard-library/map.md)

