---
title: "Класс hash_compare | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- hash_set/stdext::hash_compare
- hash_compare
dev_langs:
- C++
helpviewer_keywords:
- hash_compare class
ms.assetid: d502bb59-de57-4585-beb9-00e3a998c0af
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
ms.sourcegitcommit: 51fbd09793071631985720550007dddbe16f598f
ms.openlocfilehash: e493529a2511d92b9c99f820bd05b8f911ef9280
ms.lasthandoff: 02/24/2017

---
# <a name="hashcompare-class"></a>Класс hash_compare
Этот класс шаблона описывает объект, который может использоваться любым ассоциативным контейнером хэша — hash_map hash_multimap, hash_set или hash_multiset — в качестве объекта параметра **Traits** по умолчанию для упорядочивания и хэширования элементов, которые он содержит.  
  
## <a name="syntax"></a>Синтаксис  
  
class hash_compare { Traits comp; public: const size_t bucket_size = 4; const size_t min_buckets = 8; hash_compare(); hash_compare(Traits pred); size_t operator()(const Key& key) const; bool operator()( const Key& key1, const Key& key2) const; };  
  
## <a name="remarks"></a>Примечания  
 Каждый ассоциативный контейнер хэша хранит объект признаков хэша типа **Traits** (параметр шаблона). Можно наследовать класс от специализации hash_compare, чтобы выборочно переопределить некоторые функции и объекты, или можно предоставить собственную версию этого класса, если выполняются определенные минимальные требования. В частности, для объекта hash_comp типа **hash_compare\<Key, Traits>** указанные выше контейнеры должны реализовать следующее поведение.  
  
-   Для всех значений `key` типа **Key** вызов **hash_comp**( `key`) служит хэш-функцией, которая создает распределение значений типа **size_t**. Функция, предоставленная hash_compare, возвращает `key`.  
  
-   Для любого значения `key1` типа **Key**, которое предшествует `key2` в последовательности и имеет то же хэш-значение (возвращенное хэш-функцией), **hash_comp**( `key2`, `key1`) имеет значение false. Функция должна применить общее упорядочивание к значениям типа **Key**. Функция, предоставленная hash_compare, возвращает *comp*( `key2`, `key1`) `,`, где *comp* — это хранимый объект типа **Traits**, который можно указать при создании объекта hash_comp. Для типа параметра **Traits** **less\<Key>** по умолчанию ключи сортировки никогда не уменьшаются.  
  
-   Целочисленная константа **bucket_size** указывает среднее количество элементов на "сегмент" (запись в хэш-таблице), которое не должен превышать контейнер. Это значение должно быть больше нуля. Значение, предоставленное hash_compare, равно 4.  
  
-   Целочисленная константа **min_buckets** указывает минимальное количество сегментов в хэш-таблице. Оно должно быть степенью числа два и больше нуля. Значение, предоставленное hash_compare, равно 8.  
  
 В Visual C++ .NET 2003 члены файлов заголовков [<hash_map>](../standard-library/hash-map.md) и [<hash_set>](../standard-library/hash-set.md) больше не находятся в пространстве имен std. Они перемещены в пространство имен stdext. Более подробные сведения см. в разделе [Пространство имен stdext](../standard-library/stdext-namespace.md).  
  
## <a name="example"></a>Пример  
 Примеры объявления и использования hash_compare см. в примерах [hash_map::hash_map](../standard-library/hash-map-class.md#hash_map__hash_map), [hash_multimap::hash_multimap](../standard-library/hash-multimap-class.md#hash_multimap__hash_multimap), [hash_set::hash_set](../standard-library/hash-set-class.md#hash_set__hash_set) и [hash_multiset::hash_multiset](../standard-library/hash-multiset-class.md#hash_multiset__hash_multiset).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<hash_map>  
  
 **Пространство имен:** stdext  
  
## <a name="see-also"></a>См. также  
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)




