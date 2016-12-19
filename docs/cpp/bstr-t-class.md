---
title: "Класс _bstr_t | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_bstr_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_bstr_t - класс"
  - "BSTR - объект"
  - "BSTR - объект, инкапсуляция модели COM"
ms.assetid: 58841fef-fe21-4a84-aab9-780262b5201f
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс _bstr_t
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Объект `_bstr_t` инкапсулирует [данные типа BSTR](http://msdn.microsoft.com/ru-ru/1b2d7d2c-47af-4389-a6b6-b01b7e915228).  Этот класс управляет выделением и освобождением ресурсов посредством вызовов функций для **SysAllocString**, **SysFreeString** и других API\-интерфейсов `BSTR` при необходимости.  Класс `_bstr_t` использует подсчет ссылок во избежание слишком большой нагрузки.  
  
### Создание  
  
|||  
|-|-|  
|[\_bstr\_t](../cpp/bstr-t-bstr-t.md)|Создает объект `_bstr_t`.|  
  
### Операции  
  
|||  
|-|-|  
|[Assign](../cpp/bstr-t-assign.md)|Копирует строку `BSTR` в строку `BSTR`, инкапсулированную объектом `_bstr_t`.|  
|[Attach](../cpp/bstr-t-attach.md)|Связывает упаковщик `_bstr_t` со строкой `BSTR`.|  
|[copy](../cpp/bstr-t-copy.md)|Создает копию инкапсулированного объекта `BSTR`.|  
|[Detach](../cpp/bstr-t-detach.md)|Возвращает строку `BSTR`, инкапсулированную объектом `_bstr_t`, и отсоединяет ее \(`BSTR`\) от этого объекта \(`_bstr_t`\).|  
|[GetAddress](../cpp/bstr-t-getaddress.md)|Указывает на строку `BSTR`, инкапсулированную объектом `_bstr_t`.|  
|[GetBSTR](../Topic/_bstr_t::GetBSTR.md)|Указывает на начало строки `BSTR`, инкапсулированной объектом `_bstr_t`.|  
|[length](../cpp/bstr-t-length.md)|Возвращает число символов в объекте `_bstr_t`.|  
  
### Операторы  
  
|||  
|-|-|  
|[operator \=](../cpp/bstr-t-operator-equal.md)|Присваивает новое значение существующему объекту `_bstr_t`.|  
|[operator \+\=](../cpp/bstr-t-operator-add-equal-plus.md)|Добавляет символы в конец объекта `_bstr_t`.|  
|[operator \+](../cpp/bstr-t-operator-add-equal-plus.md)|Объединяет две строки.|  
|[operator \!](../cpp/bstr-t-operator-logical-not.md)|Проверяет, является ли инкапсулированная строка `BSTR` пустой строкой \(**NULL**\).|  
|[operator \=\=, \!\=, \<, \>, \<\=, \>\=](../cpp/bstr-t-relational-operators.md)|Сравнивает два объекта `_bstr_t`.|  
|[operator wchar\_t\* &#124; char\*](../cpp/bstr-t-wchar-t-star-bstr-t-char-star.md)|Извлекает указатели на инкапсулированный объект Юникода или многобайтовый объект `BSTR`.|  
  
## Завершение блока, относящегося только к системам Microsoft  
  
## Требования  
 **Заголовок:** comutil.h  
  
 **Библиотека:** comsuppw.lib или comsuppwd.lib \(дополнительные сведения см. в разделе [\/Zc:wchar\_t \(wchar\_t – это собственный тип\)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)\)  
  
## См. также  
 [Классы поддержки компилятора COM](../cpp/compiler-com-support-classes.md)