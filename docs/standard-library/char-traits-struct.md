---
title: "Структура char_traits | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::char_traits"
  - "std.char_traits"
  - "iosfwd/std::char_traits"
  - "char_traits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "char_traits - класс"
  - "char_traits - структура"
ms.assetid: 568e59f0-4521-4207-9223-9dcf6a16d620
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# Структура char_traits
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Структура char\_traits описывает атрибуты, связанные с символом.  
  
## Синтаксис  
  
```  
template <  
   class CharType  
> struct char_traits;  
```  
  
#### Параметры  
 `CharType`  
 Тип данных элемента.  
  
## Заметки  
 Структура шаблона описывает различные признаки символов для типа **CharType**.  Класс шаблона [basic\_string](../standard-library/basic-string-class.md), а также несколько классов шаблонов iostream, включая [basic\_ios](../Topic/basic_ios%20Class.md), используют эти сведения для управления элементами типа **CharType**.  Для такого типа элемента не требуются явное создание или уничтожение.  Он должен предоставлять конструктор по умолчанию, конструктор копирования и оператор присваивания с ожидаемой семантикой.  Побитовое копирование должно иметь такой же эффект, как и присваивание.  Ни одна из функций — членов структуры char\_traits не может создавать исключения.  
  
### Typedefs  
  
|||  
|-|-|  
|[char\_type](../Topic/char_traits::char_type.md)|Тип символа.|  
|[int\_type](../Topic/char_traits::int_type.md)|Целочисленный тип, который может представлять символ типа `char_type` или символ конца файла \(EOF\).|  
|[off\_type](../Topic/char_traits::off_type.md)|Целочисленный тип, который может представлять смещения между позициями в потоке.|  
|[pos\_type](../Topic/char_traits::pos_type.md)|Целочисленный тип, который может представлять позиции в потоке.|  
|[state\_type](../Topic/char_traits::state_type.md)|Тип, представляющий состояние преобразования в многобайтовые символы в потоке.|  
  
### Функции\-члены  
  
|||  
|-|-|  
|[assign](../Topic/char_traits::assign.md)|Присваивает значение одного символа другому.|  
|[compare](../Topic/char_traits::compare.md)|Сравнивает указанное количество символов в двух строках.|  
|[copy](../Topic/char_traits::copy.md)|Копирует указанное количество символов из одной строки в другую.  Не рекомендуется.  Используйте [char\_traits::\_Copy\_s](../Topic/char_traits::_Copy_s.md) вместо него.|  
|[\_Copy\_s](../Topic/char_traits::_Copy_s.md)|Копирует указанное количество символов из одной строки в другую.|  
|[eof](../Topic/char_traits::eof.md)|Возвращает символ конца файла \(EOF\).|  
|[eq](../Topic/char_traits::eq.md)|Проверяет два символа `char_type` на равенство.|  
|[eq\_int\_type](../Topic/char_traits::eq_int_type.md)|Проверяет два символа, представленные как `int_type`, на равенство.|  
|[find](../Topic/char_traits::find.md)|Выполняет поиск первого вхождения указанного символа в диапазоне символов.|  
|[length](../Topic/char_traits::length.md)|Возвращает длину строки.|  
|[lt](../Topic/char_traits::lt.md)|Проверяет, меньше ли один символ другого.|  
|[move](../Topic/char_traits::move.md)|Копирует указанное количество символов в последовательности в другую, возможно, перекрывающуюся, последовательность.  Не рекомендуется.  Используйте [char\_traits::\_Move\_s](../Topic/char_traits::_Move_s.md) вместо него.|  
|[\_Move\_s](../Topic/char_traits::_Move_s.md)|Копирует указанное количество символов в последовательности в другую, возможно, перекрывающуюся, последовательность.|  
|[not\_eof](../Topic/char_traits::not_eof.md)|Проверяет, является ли символ символом конца файла \(EOF\).|  
|[to\_char\_type](../Topic/char_traits::to_char_type.md)|Преобразует символ `int_type` в соответствующий символ `char_type` и возвращает результат.|  
|[to\_int\_type](../Topic/char_traits::to_int_type.md)|Преобразует символ `char_type` в соответствующий символ `int_type` и возвращает результат.|  
  
## Требования  
 **Заголовок:** \<string\>  
  
 **Пространство имен:** std  
  
## См. также  
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)