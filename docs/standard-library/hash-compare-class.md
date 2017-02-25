---
title: "Класс hash_compare | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "hash_set/stdext::hash_compare"
  - "std.hash_compare"
  - "hash_compare"
  - "std::hash_compare"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "hash_compare - класс"
ms.assetid: d502bb59-de57-4585-beb9-00e3a998c0af
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# Класс hash_compare
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Этот класс шаблона описывает объект, который может использоваться любым ассоциативным контейнером хэша — hash\_map hash\_multimap, hash\_set или hash\_multiset — в качестве объекта параметра **Traits** по умолчанию для упорядочивания и хэширования элементов, которые он содержит.  
  
## Синтаксис  
  
```  
template<class Key, class Traits = less<Key> >  
   class hash_compare  
   {  
   Traits comp;  
public:  
   const size_t bucket_size = 4;  
   const size_t min_buckets = 8;  
   hash_compare( );  
   hash_compare( Traits pred );  
   size_t operator( )( const Key& _Key ) const;  
   bool operator( )(   
      const Key& _Key1,  
      const Key& _Key2  
   ) const;  
   };  
```  
  
## Заметки  
 Каждый ассоциативный контейнер хэша хранит объект признаков хэша типа**Traits** \(параметр шаблона\).  Можно наследовать класс от специализации hash\_compare, чтобы выборочно переопределить некоторые функции и объекты, или можно предоставить собственную версию этого класса, если выполняются определенные минимальные требования.  В частности, для объекта hash\_comp типа **hash\_compare\<Key, Traits\>** указанные выше контейнеры должны реализовать следующее поведение.  
  
-   Для всех значений `_Key` типа **Key** вызов **hash\_comp**\(`_Key`\) служит хэш\-функцией, которая создает распределение значений типа **size\_t**.  Функция, предоставленная hash\_compare, возвращает `_Key`.  
  
-   Для любого значения `_Key1` типа **Key**, которое предшествует `_Key2` в последовательности и имеет то же хэш\-значение \(возвращенное хэш\-функцией\), **hash\_comp**\(`_Key2`, `_Key1`\) имеет значение false.  Функция должна применить общее упорядочивание к значениям типа **Key**.  Функция, предоставленная hash\_compare, возвращает *comp*\(`_Key2`, `_Key1`\)`,`, где *comp* — это хранимый объект типа **Traits**, который можно указать при создании объекта hash\_comp.  Для типа параметра **Traits less\<Key\>** по умолчанию ключи сортировки никогда не уменьшаются.  
  
-   Целочисленная константа **bucket\_size** указывает среднее количество элементов на «сегмент» \(запись в хэш\-таблице\) для контейнера.  Это значение должно быть больше нуля.  Значение, предоставленное hash\_compare, равно 4.  
  
-   Целочисленная константа **min\_buckets** указывает минимальное количество сегментов в хэш\-таблице.  Оно должно быть степенью числа два и больше нуля.  Значение, предоставленное hash\_compare, равно 8.  
  
 В Visual C\+\+ .NET 2003 члены файлов заголовков [\<hash\_map\>](../standard-library/hash-map.md) и [\<hash\_set\>](../standard-library/hash-set.md) больше не находятся в пространстве имен std. Они перемещены в пространство имен stdext.  Дополнительные сведения см. в разделе [Пространство имен stdext](../Topic/stdext%20Namespace.md).  
  
## Пример  
 Примеры объявления и использования hash\_compare см. в примерах [hash\_map::hash\_map](../Topic/hash_map::hash_map.md), [hash\_multimap::hash\_multimap](../Topic/hash_multimap::hash_multimap.md), [hash\_set::hash\_set](../Topic/hash_set::hash_set.md) и [hash\_multiset::hash\_multiset](../Topic/hash_multiset::hash_multiset.md).  
  
## Требования  
 **Заголовок:** \<hash\_map\>  
  
 **Пространство имен:** stdext  
  
## См. также  
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Библиотека стандартных шаблонов](../misc/standard-template-library.md)