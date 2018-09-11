---
title: 'по умолчанию:: (имя_типа):: Equals метод | Документация Майкрософт'
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
f1_keywords:
- VCCORLIB/Platform::Object::Equals
dev_langs:
- C++
ms.assetid: 4450f835-06fc-4758-8d0a-72cf00007873
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 127f5ee876790fa3cfb8a052c2db6c41cc00f332
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44109023"
---
# <a name="defaulttypenameequals-method"></a>Метод default::(type_name)::Equals

Определяет, равен ли заданный объект текущему объекту.

## <a name="syntax"></a>Синтаксис

```cpp
bool Equals(
    Object^ obj
)
```

### <a name="parameters"></a>Параметры

*obj*<br/>
Объект для сравнения.

### <a name="return-value"></a>Возвращаемое значение

Значение`true` , если объекты равны; в противном случае — значение `false`.

### <a name="requirements"></a>Требования

**Минимальный поддерживаемый клиент:** Windows 8

**Минимальный поддерживаемый сервер:** Windows Server 2012

**Пространство имен:** по умолчанию

**Заголовок:** vccorlib.h

## <a name="see-also"></a>См. также

[Пространство имен по умолчанию](../cppcx/default-namespace.md)