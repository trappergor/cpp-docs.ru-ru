---
title: Platform::CallbackContext - перечисление
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::CallbackContext
helpviewer_keywords:
- Platform::CallbackContext Enumeration
ms.assetid: 60e0c7cb-5d8f-482a-bdca-ca9335ae4899
ms.openlocfilehash: 1daa3988fcb985dab9d3083233a3703a20cc2fdb
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214287"
---
# <a name="platformcallbackcontext-enumeration"></a>Platform::CallbackContext - перечисление

Указывает контекст потока, в котором выполняется функция обратного вызова (обработчик события).

## <a name="syntax"></a>Синтаксис

```cpp
enum class CallbackContext {};
```

### <a name="members"></a>Члены

|Код типа|Description|
|---------------|-----------------|
|Любой|Функция обратного вызова может выполняться в любом контексте потока.|
|Аналогично|Функция обратного вызова может выполняться в контексте потока, запустившего асинхронную операцию.|

### <a name="requirements"></a>Требования

**Минимальный поддерживаемый клиент:** Windows 8

**Минимальный поддерживаемый сервер:** Windows Server 2012

**Пространство имен:** Platform

**Метаданные:** platform.winmd
