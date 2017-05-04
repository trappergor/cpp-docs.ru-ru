---
title: "Перечисление Platform::TypeCode | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::TypeCode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Перечисление Platform::TypeCode"
ms.assetid: 93c1305f-eb16-4bec-aead-f88d9518b4cf
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 3
---
# Перечисление Platform::TypeCode
Указывает категорию чисел, представляющую встроенный тип.  
  
## Синтаксис  
  
```cpp  
enum class TypeCode {};  
```  
  
## Члены  
  
|Код типа|Описание|  
|--------------|--------------|  
|Boolean|Тип Platform::Boolean.|  
|Char16|Тип default::char16.|  
|DateTime|Тип DateTime.|  
|Десятичное число|Числовой тип.|  
|Double|Тип default::float64.|  
|Empty|Void|  
|Int16|Тип default::int16.|  
|Int32|Тип default::int32.|  
|Int64|Тип default::int64.|  
|Int8|Тип default::int8.|  
|Объект|Тип Platform::Object.|  
|Single|Тип default::float32.|  
|Строка|Тип Platform::String.|  
|UInt16|Тип default::uint16.|  
|UInt32|Тип default::uint32.|  
|UInt64|Тип default::uint64.|  
|UInt8|Тип default::uint8.|  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Метаданные:** platform.winmd