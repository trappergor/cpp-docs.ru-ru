---
title: Перечисление Platform::TypeCode | Документы Microsoft
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::TypeCode
dev_langs:
- C++
helpviewer_keywords:
- Platform::TypeCode Enumeration
ms.assetid: 93c1305f-eb16-4bec-aead-f88d9518b4cf
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 033241f0be5653f27a117ef9710837817b5abff6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="platformtypecode-enumeration"></a>Перечисление Platform::TypeCode
Указывает категорию чисел, представляющую встроенный тип.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
enum class TypeCode {};  
```  
  
### <a name="members"></a>Участники  
  
|Код типа|Описание|  
|---------------|-----------------|  
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
|Object|Тип Platform::Object.|  
|Single|Тип default::float32.|  
|String|Тип Platform::String.|  
|UInt16|Тип default::uint16.|  
|UInt32|Тип default::uint32.|  
|UInt64|Тип default::uint64.|  
|UInt8|Тип default::uint8.|  
  
### <a name="requirements"></a>Требования  
 **Минимальный поддерживаемый клиент:** Windows 8  
  
 **Минимальный поддерживаемый сервер:** Windows Server 2012  
  
 **Пространство имен:** Platform  
  
 **Метаданные:** platform.winmd