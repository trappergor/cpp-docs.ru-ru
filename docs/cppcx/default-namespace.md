---
title: "Пространство имен default | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "default_CPP"
dev_langs: 
  - "C++"
ms.assetid: 4712e9dc-57ba-43cc-811e-022e1dae4de8
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 6
---
# Пространство имен default
Пространство имен `default` охватывает встроенные типы, поддерживаемые [!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)] \([!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\).  
  
## Синтаксис  
  
```  
namespace default;  
```  
  
## Члены  
 Все встроенные типы наследуют следующие члены.  
  
|||  
|-|-|  
|[Метод default::\(type\_name\)::Equals](../cppcx/default-type-name-equals-method.md)|Определяет, равен ли заданный объект текущему объекту.|  
|[Метод default::\(имя\_типа\)::GetHashCode](../cppcx/default-type-name-gethashcode-method.md)|Возвращает хэш\-код данного экземпляра.|  
|[Метод default::\(type\_name\)::GetType](../cppcx/default-type-name-gettype-method.md)|Возвращает строку, которая представляет текущий тип.|  
|[Метод default::\(имя\_типа\)::ToString](../cppcx/default-type-name-tostring-method.md)|Возвращает строку, которая представляет текущий тип.|  
  
### Встроенные типы  
  
|Имя|Описание|  
|---------|--------------|  
|`char16`|16\-битовое нечисловое значение, представляющее кодовую точку Юникода \(UTF\-16\).|  
|`float32`|32\-битовое число с плавающей запятой стандарта IEEE 754.|  
|`float64`|64\-битовое число с плавающей запятой стандарта IEEE 754.|  
|`int16`|16\-разрядное знаковое целое число.|  
|`int32`|32\-разрядное знаковое целое число.|  
|`int64`|64\-разрядное целое число со знаком.|  
|`int8`|8\-разрядное числовое значение со знаком.|  
|`uint16`|16\-разрядное целое число без знака.|  
|`uint32`|32\-разрядное целое число без знака.|  
|`uint64`|64\-разрядное целое число без знака.|  
|`uint8`|8\-разрядное числовое значение без знака.|  
  
## Требования  
 **Заголовок:** vccorlib.h  
  
## См. также  
 [Справочник по языку C\+\+](../cppcx/visual-c-language-reference-c-cx.md)