---
title: "Структура atomic | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: atomic/std::atomic
dev_langs: C++
ms.assetid: 261628ed-7049-41ac-99b9-cfe49f696b44
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3299f1bad01427723d3fcfabefd7924913d5690f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="atomic-structure"></a>Структура atomic
Описывает объект, который выполняет атомарные операции с сохраненным значением типа `Ty`.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class Ty>
struct atomic;
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[atomic](http://msdn.microsoft.com/Library/a538c43f-4d48-4308-ae1b-bab1839bccb8)|Создает атомарный объект.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[оператор atomic::operator Ty](http://msdn.microsoft.com/Library/a366c700-c7a0-4bcb-8eb4-4b57dfaea065)|Считывает и возвращает сохраненное значение. ([atomic::load](http://msdn.microsoft.com/Library/05212726-cf8a-46fe-83d2-c16ac2abb7d1))|  
|[оператор atomic::operator=](http://msdn.microsoft.com/Library/fe161d57-47ae-4bad-92bf-ce32ac8d5953)|Использует указанное значение для замены сохраненного значения. ([atomic::store](http://msdn.microsoft.com/Library/84759413-d664-47ef-a1f3-a73c5a62007b))|  
|[оператор atomic::operator++](http://msdn.microsoft.com/Library/492959e9-1ea8-4e02-a031-82b1b92e91a0)|Увеличивает сохраненное значение. Используется только специализациями для целочисленных типов и указателей.|  
|[оператор atomic::operator+=](http://msdn.microsoft.com/Library/9ec97aa2-c9d7-436b-943d-2989eb2617dd)|Добавляет указанное значение к сохраненному значению. Используется только специализациями для целочисленных типов и указателей.|  
|[оператор atomic::operator--](http://msdn.microsoft.com/Library/ad7c1ea7-1f6d-4a54-bf26-07630f749864)|Уменьшает сохраненное значение. Используется только специализациями для целочисленных типов и указателей.|  
|[оператор atomic::operator-=](http://msdn.microsoft.com/Library/902d0d9f-88fd-4500-aa2d-1e50f443e77c)|Вычитает указанное значение из сохраненного значения. Используется только специализациями для целочисленных типов и указателей.|  
|[оператор atomic::operator&=](http://msdn.microsoft.com/Library/90e730ac-12e1-4abb-98f5-4eadd6861a89)|Выполняет побитовую операцию `and` с указанным значением и сохраненным значением. Используется только специализациями для целочисленных типов.|  
|[оператор atomic::operator&#124;=](http://msdn.microsoft.com/Library/f105eacc-31a6-4906-abba-f1cf013599b2)|Выполняет побитовую операцию `or` с указанным значением и сохраненным значением. Используется только специализациями для целочисленных типов.|  
|[оператор atomic::operator^=](http://msdn.microsoft.com/Library/f2a4da9d-67e8-4249-9161-9998e72a33c2)|Выполняет побитовую операцию `exclusive or` с указанным значением и сохраненным значением. Используется только специализациями для целочисленных типов.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[compare_exchange_strong](http://msdn.microsoft.com/Library/47bbf894-b28c-4ece-959e-67b3863cf4ed)|Выполняет операцию `atomic_compare_and_exchange` с `this` и возвращает результат.|  
|[compare_exchange_weak](http://msdn.microsoft.com/Library/e15e421a-f7a3-4272-993a-f487d2242e4f)|Выполняет операцию `weak_atomic_compare_and_exchange` с `this` и возвращает результат.|  
|[fetch_add](http://msdn.microsoft.com/Library/c68b91f2-6e8a-4ffa-8991-6bb6d466e1f3)|Добавляет указанное значение к сохраненному значению.|  
|[fetch_and](http://msdn.microsoft.com/Library/a9c83001-b72c-4085-9640-f63f866714b9)|Выполняет побитовую операцию `and` с указанным значением и сохраненным значением.|  
|[fetch_or](http://msdn.microsoft.com/Library/4c532f7f-80c5-432a-b34b-48feacab8dca)|Выполняет побитовую операцию `or` с указанным значением и сохраненным значением.|  
|[fetch_sub](http://msdn.microsoft.com/Library/8cc80d4b-0942-45a3-9db8-bbf339a903e4)|Вычитает указанное значение из сохраненного значения.|  
|[fetch_xor](http://msdn.microsoft.com/Library/92bbaff8-ee29-4a1e-aee4-d9d405285bfe)|Выполняет побитовую операцию `exclusive or` с указанным значением и сохраненным значением.|  
|[is_lock_free](http://msdn.microsoft.com/Library/b99d5130-cdda-40a2-b14c-152b13a8ba45)|Указывает, являются ли атомарные операции с `this` *неблокирующими*. Атомарный тип является *неблокирующим*, если никакие атомарные операции с этим типом не используют блокировки.|  
|[загрузить](http://msdn.microsoft.com/Library/05212726-cf8a-46fe-83d2-c16ac2abb7d1)|Считывает и возвращает сохраненное значение.|  
|[store](http://msdn.microsoft.com/Library/84759413-d664-47ef-a1f3-a73c5a62007b)|Использует указанное значение для замены сохраненного значения.|  
  
## <a name="remarks"></a>Примечания  
 Тип `Ty` должен быть *доступен для простого копирования*. То есть при использовании [memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md) для копирования его байтов должен создаваться допустимый объект `Ty`, эквивалентный исходному объекту. Функции-члены `compare_exchange_weak` и `compare_exchange_strong` используют [memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md) для определения, равны ли два значения `Ty`. Эти функции не будут использовать заданный в `Ty` `operator==`. Функции-члены `atomic` используют `memcpy` для копирования значений типа `Ty`.  
  
 Частичная специализация `atomic<Ty *>` существует для всех типов указателей. Специализация позволяет добавлять смещение к значению управляемого указателя или вычитать из него смещение. Арифметические операции принимают аргумент типа `ptrdiff_t` и настраивают этот аргумент в соответствии с размером `Ty` для согласования с обычным вычислением адресов.  
  
 Специализация существует для любого целочисленного типа, кроме `bool`. Каждая специализация предоставляет широкий набор методов для атомарных арифметических и логических операций.  
  
||||  
|-|-|-|  
|`atomic<char>`|`atomic<signed char>`|`atomic<unsigned char>`|  
|`atomic<char16_t>`|`atomic<char32_t>`|`atomic<wchar_t>`|  
|`atomic<short>`|`atomic<unsigned short>`|`atomic<int>`|  
|`atomic<unsigned int>`|`atomic<long>`|`atomic<unsigned long>`|  
|`atomic<long long>`|`atomic<unsigned long long>`|  
  
 Специализации для целочисленных типов являются производными от соответствующих типов `atomic_integral`. Например, `atomic<unsigned int>` является производной от `atomic_uint`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<atomic >  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [\<atomic>](../standard-library/atomic.md)   
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)



