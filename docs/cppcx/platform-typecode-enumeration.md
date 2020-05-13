---
title: Перечисление Platform::TypeCode
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::TypeCode
helpviewer_keywords:
- Platform::TypeCode Enumeration
ms.assetid: 93c1305f-eb16-4bec-aead-f88d9518b4cf
ms.openlocfilehash: 86bc17c45f36a5a72b089340e166df11e9a4334d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214290"
---
# <a name="platformtypecode-enumeration"></a>Перечисление Platform::TypeCode

Указывает категорию чисел, представляющую встроенный тип.

## <a name="syntax"></a>Синтаксис

```cpp
enum class TypeCode {};
```

### <a name="members"></a>Члены

|Код типа|Description|
|---------------|-----------------|
|Логическое|Тип Platform::Boolean.|
|Char16|Тип default::char16.|
|Дата и время|Тип DateTime.|
|Decimal|Числовой тип.|
|Double|Тип default::float64.|
|Empty|Void|
|Int16|Тип default::int16.|
|Int32|Тип default::int32.|
|Int64|Тип default::int64.|
|Int8|Тип default::int8.|
|Объект|Тип Platform::Object.|
|Один|Тип default::float32.|
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
