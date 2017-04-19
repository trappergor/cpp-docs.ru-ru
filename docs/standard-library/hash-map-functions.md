---
title: "Функции &lt;hash_map&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- hash_map/std::swap
- hash_map/std::swap (hash_map)
ms.assetid: 28748cd0-71f7-41b9-b068-579183645fba
caps.latest.revision: 9
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 85c900f2263ae1c1089478badc85388e3b5e8548
ms.openlocfilehash: 6c11e1f90ce05aa3a4dc22ce31bed104ef0fa795
ms.lasthandoff: 02/24/2017

---
# <a name="lthashmapgt-functions"></a>Функции &lt;hash_map&gt;
|||  
|-|-|  
|[swap](#swap)|[swap (hash_map)](#swap__hash_map_)|  
  
##  <a name="swap__hash_map_"></a>  swap (hash_map)  
  
> [!NOTE]
>  Этот API устарел. Вместо него следует использовать [класс unordered_map](../standard-library/unordered-map-class.md).  
  
 Меняет местами элементы двух hash_map.  
  
```
void swap(
    hash_map <Key, Type, Traits, Alloctor>& left,
    hash_map <Key, Type, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Параметры  
 `right`  
 hash_map, элементы которой должны быть заменены на элементы схемы `left`.  
  
 `left`  
 hash_map, элементы которой должны быть заменены на элементы схемы `right`.  
  
### <a name="remarks"></a>Примечания  
 Функция-шаблон является специальным алгоритмом для схемы hash_map класса контейнера для выполнения функции-члена `left.`[swap](../standard-library/basic-ios-class.md#basic_ios__swap)*(right*). Это экземпляр частичного упорядочивания шаблонов функций компилятором. Когда функции-шаблоны перегружаются таким образом, что соответствие шаблона и вызова функции не является уникальным, компилятор выберет наиболее специализированную версию функции-шаблона. Общая версия функции шаблона, **template \<class T> void swap(T&, T&)**, в файле заголовка алгоритма работает посредством присвоения и выполняется медленно. Специализированная версия в каждом контейнере работает гораздо быстрее, так как она может работать с внутренним представлением класса контейнера.  
  
 В Visual C++ .NET 2003 члены файлов заголовков [<hash_map>](../standard-library/hash-map.md) и [<hash_set>](../standard-library/hash-set.md) больше не находятся в пространстве имен std. Они перемещены в пространство имен stdext. Дополнительные сведения см. в разделе [Пространство имен stdext](../standard-library/stdext-namespace.md).  
  
##  <a name="swap"></a>  swap  
  
> [!NOTE]
>  Этот API устарел. Вместо него следует использовать [класс unordered_multimap](../standard-library/unordered-multimap-class.md).  
  
 Меняет местами элементы двух hash_multimap.  
  
```
void swap(
    hash_multimap <Key, Type, Traits, Alloctor>& left,
    hash_multimap <Key, Type, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Параметры  
 `right`  
 hash_multimap, элементы которой должны быть заменены на элементы схемы `left`.  
  
 `left`  
 hash_multimap, элементы которой должны быть заменены на элементы схемы `right`.  
  
### <a name="remarks"></a>Примечания  
 Функция-шаблон является специальным алгоритмом для схемы hash_multimap класса контейнера для выполнения функции-члена `left.`[swap](../standard-library/hash-multimap-class.md#hash_multimap__swap)*(right*`)`. Это экземпляр частичного упорядочивания шаблонов функций компилятором. Когда функции-шаблоны перегружаются таким образом, что соответствие шаблона и вызова функции не является уникальным, компилятор выберет наиболее специализированную версию функции-шаблона. Общая версия функции шаблона, **template \<class T> void swap(T&, T&)**, в файле заголовка алгоритма работает посредством присвоения и выполняется медленно. Специализированная версия в каждом контейнере работает гораздо быстрее, так как она может работать с внутренним представлением класса контейнера.  
  
 В Visual C++ .NET 2003 члены файлов заголовков [<hash_map>](../standard-library/hash-map.md) и [<hash_set>](../standard-library/hash-set.md) больше не находятся в пространстве имен std. Они перемещены в пространство имен stdext. Дополнительные сведения см. в разделе [Пространство имен stdext](../standard-library/stdext-namespace.md).  
  
## <a name="see-also"></a>См. также  
 [<hash_map>](../standard-library/hash-map.md)




