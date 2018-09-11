---
title: Перечисление Platform::CallbackContext | Документация Майкрософт
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::CallbackContext
dev_langs:
- C++
helpviewer_keywords:
- Platform::CallbackContext Enumeration
ms.assetid: 60e0c7cb-5d8f-482a-bdca-ca9335ae4899
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fe988a7dee7fb358d9454c06811d7baf2cd4ace0
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44101967"
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