---
title: Перечисление Platform::TypeCode | Документация Майкрософт
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0e874b3dc479755f688128b3e6690eee89929c1c
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42606186"
---
# <a name="platformtypecode-enumeration"></a>Перечисление Platform::TypeCode
Указывает категорию чисел, представляющую встроенный тип.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
enum class TypeCode {};  
```  
  
### <a name="members"></a>Участники  
  
|Код типа|Описание:|  
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