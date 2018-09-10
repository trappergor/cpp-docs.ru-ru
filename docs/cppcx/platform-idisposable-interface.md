---
title: Интерфейс Platform::IDisposable | Документация Майкрософт
ms.custom: ''
ms.date: 02/03/2017
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::IDisposable
dev_langs:
- C++
helpviewer_keywords:
- Platform::IDisposable Interface
ms.assetid: f4344056-7030-42ed-bc98-b140edffddcd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c596e4054729855ea3c8caedf632ca8dd50b796a
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44105072"
---
# <a name="platformidisposable-interface"></a>Интерфейс Platform::IDisposable

Используется для освобождения неуправляемых ресурсов.

## <a name="syntax"></a>Синтаксис

```cpp
public interface class IDisposable
```

## <a name="attributes"></a>Атрибуты

**GuidAttribute**(«de0cbaea-8065-4a45-b196-c9d443f9bab3»)

**VersionAttribute**(NTDDI_WIN8)

### <a name="members"></a>Участники

Интерфейс IDisposable наследует от интерфейса IUnknown. Интерфейс IDisposable также имеет следующие типы членов.

**Методы**

Интерфейс IDisposable содержит следующие методы.

|Метод|Описание|
|------------|-----------------|
|Ликвидировать|Используется для освобождения неуправляемых ресурсов.|

### <a name="requirements"></a>Требования

**Минимальный поддерживаемый клиент:** Windows 8

**Минимальный поддерживаемый сервер:** Windows Server 2012

**Пространство имен:** Platform