---
title: "Функции &lt;hash_set&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- hash_set/std::swap
- hash_set/std::swap (hash_multiset)
ms.assetid: 557a0162-3728-4537-97dc-f9f6cc7ece94
caps.latest.revision: "7"
manager: ghogen
ms.openlocfilehash: 4fcd6f0d72d31823a0d35108f087f2ad680e2f48
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2017
---
# <a name="lthashsetgt-functions"></a>Функции &lt;hash_set&gt;
|||  
|-|-|  
|[swap](#swap)|[swap (hash_multiset)](#swap_hash_multiset)|  
  
##  <a name="swap"></a>  swap  
  
> [!NOTE]
>  Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).  
  
 Выполняет обмен элементами между двумя объектами hash_set.  
  
```
void swap(
    hash_set <Key, Traits, Allocator>& left,
    hash_set <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Параметры  
 `right`  
 Объект hash_set, предоставляющий элементы для обмена местами, или hash_set, элементы которого должны быть заменены на элементы hash_set `left`.  
  
 `left`  
 hash_set, элементы которого должны быть заменены на элементы hash_set `right`.  
  
### <a name="remarks"></a>Примечания  
 Функция-шаблон `swap` является специальным алгоритмом для объекта hash_set класса контейнера для выполнения функции-члена `left.`[swap](../standard-library/hash-set-class.md#swap)(`right`). Это экземпляр частичного упорядочивания шаблонов функций компилятором. Когда функции-шаблоны перегружаются таким образом, что соответствие шаблона и вызова функции не является уникальным, компилятор выберет наиболее специализированную версию функции-шаблона. Общая версия функции-шаблона  
  
 **template \<class T> void swap(T&, T&),**  
  
 в классе алгоритма работает путем назначения и является медленной операцией. Специализированная версия в каждом контейнере работает гораздо быстрее, так как она может работать с внутренним представлением класса контейнера.  
  
   
  
### <a name="example"></a>Пример  
  См. пример кода для функции-члена [hash_set::swap](../standard-library/hash-set-class.md#swap), в котором используется версия шаблона `swap`.  
  
##  <a name="swap_hash_multiset"></a>  swap (hash_multiset)  
  
> [!NOTE]
>  Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).  
  
 Меняет местами элементы двух объектов hash_multiset.  
  
```
void swap(hash_multiset <Key, Traits, Allocator>& left, hash_multiset <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Параметры  
 `right`  
 Объект hash_multiset, предоставляющий элементы для обмена местами, или hash_multiset, элементы которого должны быть заменены на элементы hash_multiset `left`.  
  
 `left`  
 hash_multiset, элементы которого должны быть заменены на элементы hash_multiset `right`.  
  
### <a name="remarks"></a>Примечания  
 Функция-шаблон `swap` является специальным алгоритмом для объекта hash_multiset класса контейнера для выполнения функции-члена `left.`[swap](../standard-library/hash-multiset-class.md#swap)(`right`). Это экземпляр частичного упорядочивания шаблонов функций компилятором. Когда функции-шаблоны перегружаются таким образом, что соответствие шаблона и вызова функции не является уникальным, компилятор выберет наиболее специализированную версию функции-шаблона. Общая версия функции-шаблона  
  
 **template \<class T> void swap(T&, T&),**  
  
 в классе алгоритма работает путем назначения и является медленной операцией. Специализированная версия в каждом контейнере работает гораздо быстрее, так как она может работать с внутренним представлением класса контейнера.  
  
   
  
### <a name="example"></a>Пример  
  См. пример кода для функции-члена [hash_multiset::swap](../standard-library/hash-multiset-class.md#swap), в котором используется версия шаблона `swap`.  
  
## <a name="see-also"></a>См. также  
 [<hash_set>](../standard-library/hash-set.md)



