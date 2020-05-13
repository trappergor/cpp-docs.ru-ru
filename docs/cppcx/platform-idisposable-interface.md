---
title: Platform::IDisposable - интерфейс
ms.date: 02/03/2017
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::IDisposable
helpviewer_keywords:
- Platform::IDisposable Interface
ms.assetid: f4344056-7030-42ed-bc98-b140edffddcd
ms.openlocfilehash: 0024edbad0bb3311a0497be67fc8bcfc954602e1
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214244"
---
# <a name="platformidisposable-interface"></a>Platform::IDisposable - интерфейс

Используется для освобождения неуправляемых ресурсов.

## <a name="syntax"></a>Синтаксис

```cpp
public interface class IDisposable
```

## <a name="attributes"></a>Атрибуты

**GuidAttribute**("de0cbaea-8065-4a45-b196-c9d443f9bab3")

**Версионаттрибуте**(NTDDI_WIN8)

### <a name="members"></a>Члены

Интерфейс IDisposable наследует от интерфейса IUnknown. Интерфейс IDisposable также имеет следующие типы членов.

**Методы**

Интерфейс IDisposable содержит следующие методы.

|Метод|Description|
|------------|-----------------|
|Dispose|Используется для освобождения неуправляемых ресурсов.|

### <a name="requirements"></a>Требования

**Минимальный поддерживаемый клиент:** Windows 8

**Минимальный поддерживаемый сервер:** Windows Server 2012

**Пространство имен:** Platform
