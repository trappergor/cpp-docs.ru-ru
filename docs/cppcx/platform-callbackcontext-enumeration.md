---
title: Platform::CallbackContext - перечисление
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::CallbackContext
helpviewer_keywords:
- Platform::CallbackContext Enumeration
ms.assetid: 60e0c7cb-5d8f-482a-bdca-ca9335ae4899
ms.openlocfilehash: 7f4e020ab0b1e377456c27d3b4666e15b5a4f7a1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50441358"
---
# <a name="platformcallbackcontext-enumeration"></a>Platform::CallbackContext - перечисление

Указывает контекст потока, в котором выполняется функция обратного вызова (обработчик события).

## <a name="syntax"></a>Синтаксис

```cpp
enum class CallbackContext {};
```

### <a name="members"></a>Участники

|Код типа|Описание|
|---------------|-----------------|
|Любой|Функция обратного вызова может выполняться в любом контексте потока.|
|То же|Функция обратного вызова может выполняться в контексте потока, запустившего асинхронную операцию.|

### <a name="requirements"></a>Требования

**Минимальный поддерживаемый клиент:** Windows 8

**Минимальный поддерживаемый сервер:** Windows Server 2012

**Пространство имен:** Platform

**Метаданные:** platform.winmd