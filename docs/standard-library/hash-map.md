---
title: "&lt;hash_map&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 09/18/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <hash_map>
- std::<hash_map>
dev_langs: C++
helpviewer_keywords: hash_map header
ms.assetid: 0765708a-a668-42a2-9800-654c857bdcc2
caps.latest.revision: "27"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a996142e128f4113fb9d1057cd061155dae251f1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="lthashmapgt"></a>&lt;hash_map&gt;
> [!NOTE]
>  Этот заголовок устарел. Вместо него следует использовать [ \<unordered_map >](unordered-map.md).  
  
 Определяет контейнер шаблонных классов hash_map и hash_multimap и их поддерживаемые шаблоны.  
 
  
## <a name="syntax"></a>Синтаксис  
  
```  
#include <hash_map>  
  
```  
  
### <a name="operators"></a>Операторы  
  
|Версия hash_map|Версия hash_multimap|Описание:|  
|-----------------------|----------------------------|-----------------|  
|[operator!= (hash_map)](hash-map-operators.md#op_neq)|[Operator!=(hash_multimap)](hash-map-operators.md#op_neq_mm)|Проверяет неравенство объекта hash_map или hash_multimap слева от оператора объекту hash_map или hash_multimap справа от оператора.|  
|[ operator== (hash_map)](hash-map-operators.md#op_eq_eq)|[оператор == (hash_multimap)] ((хэш карты operators.md op_eq_eq_mm #)|Проверяет равенство объекта hash_map или hash_multimap слева от оператора объекту hash_map или hash_multimap справа от оператора.|  
  
### <a name="specialized-template-functions"></a>Специализированные функции шаблонов  
  
|Версия hash_map|Версия hash_multimap|Описание:|  
|-----------------------|----------------------------|-----------------|  
|[swap (hash_map)](hash-map-class.md#swap)|[swap (hash_multimap)](hash-multimap-class.md#swap)|Меняет местами элементы двух объектов hash_map или hash_multimap.|  
  
### <a name="classes"></a>Классы  
  
|||  
|-|-|  
|[Класс hash_compare](hash-compare-class.md)|Описывает объект, который может использоваться любыми hash-ассоциативными контейнерами (hash_map, hash_multimap, hash_set или hash_multiset) как объект параметра **Traits** по умолчанию для сортировки и хэширования элементов в них.|  
|[Класс value_compare](value-compare-class.md)|Предоставляет объект функции, который может сравнивать элементы hash_map путем сравнения значения ключей для определения относительного порядка в hash_map.|  
|[Класс hash_map](hash-map-class.md)|Используется для хранения и быстрого считывания данных из коллекции, в которой каждый элемент — это пара, которая имеет отсортированный уникальный ключ и связанное с ним значение.|  
|[Класс hash_multimap](hash-multimap-class.md)|Используется для хранения и быстрого считывания данных из коллекции, в которой каждый элемент — это пара, которая имеет ключ, значение которого не должно быть уникальным, и связанное с ним значение.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<hash_map>  
  
 **Пространство имен:** stdext  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](cpp-standard-library-header-files.md)   
 [Потокобезопасность в стандартной библиотеке C++](thread-safety-in-the-cpp-standard-library.md)   
 [Справочник по стандартной библиотеке C++](cpp-standard-library-reference.md)



