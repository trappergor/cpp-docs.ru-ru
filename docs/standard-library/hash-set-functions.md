---
title: "Функции &lt;hash_set&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 557a0162-3728-4537-97dc-f9f6cc7ece94
caps.latest.revision: 7
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 1238f4a4e75f13ccd660554de8c49646549bc2cc
ms.lasthandoff: 02/24/2017

---
# <a name="lthashsetgt-functions"></a>Функции &lt;hash_set&gt;
|||  
|-|-|  
|[swap](#swap)|[swap (hash_multiset)](#swap__hash_multiset_)|  
  
##  <a name="a-nameswapa--swap"></a><a name="swap"></a>  swap  
  
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
 Функция-шаблон `swap` является специальным алгоритмом для объекта hash_set класса контейнера для выполнения функции-члена `left``.`[swap](../standard-library/hash-set-class.md#hash_set__swap)(`right`). Это экземпляр частичного упорядочивания шаблонов функций компилятором. Когда функции-шаблоны перегружаются таким образом, что соответствие шаблона и вызова функции не является уникальным, компилятор выберет наиболее специализированную версию функции-шаблона. Общая версия функции-шаблона  
  
 **template \<class T> void swap(T&, T&),**  
  
 в классе алгоритма работает путем назначения и является медленной операцией. Специализированная версия в каждом контейнере работает гораздо быстрее, так как она может работать с внутренним представлением класса контейнера.  
  
 В Visual C++ .NET 2003 члены файлов заголовков [<hash_map>](../standard-library/hash-map.md) и [<hash_set>](../standard-library/hash-set.md) больше не находятся в пространстве имен std. Они перемещены в пространство имен stdext. Более подробные сведения см. в разделе [Пространство имен stdext](../standard-library/stdext-namespace.md).  
  
### <a name="example"></a>Пример  
  См. пример кода для функции-члена [hash_set::swap](../standard-library/hash-set-class.md#hash_set__swap), в котором используется версия шаблона `swap`.  
  
##  <a name="a-nameswaphashmultiseta--swap-hashmultiset"></a><a name="swap__hash_multiset_"></a>  swap (hash_multiset)  
  
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
 Функция-шаблон `swap` является специальным алгоритмом для объекта hash_multiset класса контейнера для выполнения функции-члена `left``.`[swap](../standard-library/hash-multiset-class.md#hash_multiset__swap)(`right`). Это экземпляр частичного упорядочивания шаблонов функций компилятором. Когда функции-шаблоны перегружаются таким образом, что соответствие шаблона и вызова функции не является уникальным, компилятор выберет наиболее специализированную версию функции-шаблона. Общая версия функции-шаблона  
  
 **template \<class T> void swap(T&, T&),**  
  
 в классе алгоритма работает путем назначения и является медленной операцией. Специализированная версия в каждом контейнере работает гораздо быстрее, так как она может работать с внутренним представлением класса контейнера.  
  
 В Visual C++ .NET 2003 члены файлов заголовков [<hash_map>](../standard-library/hash-map.md) и [<hash_set>](../standard-library/hash-set.md) больше не находятся в пространстве имен std. Они перемещены в пространство имен stdext. Более подробные сведения см. в разделе [Пространство имен stdext](../standard-library/stdext-namespace.md).  
  
### <a name="example"></a>Пример  
  См. пример кода для функции-члена [hash_multiset::swap](../standard-library/hash-multiset-class.md#hash_multiset__swap), в котором используется версия шаблона `swap`.  
  
## <a name="see-also"></a>См. также  
 [<hash_set>](../standard-library/hash-set.md)




