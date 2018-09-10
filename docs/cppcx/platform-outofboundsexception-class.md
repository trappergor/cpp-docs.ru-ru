---
title: Класс Platform::OutOfBoundsException | Документация Майкрософт
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::OutOfBoundsException
- VCCORLIB/Platform::OutOfBoundsException::OutOfBoundsException
dev_langs:
- C++
helpviewer_keywords:
- Platform::OutOfBoundsException
ms.assetid: 96f8bf75-1207-4049-964b-7771822cadf3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e1a7fad8f4d0bdc0c91dab50f5737b6aa4476438
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44105774"
---
# <a name="platformoutofboundsexception-class"></a>Класс Platform::OutOfBoundsException

Возникает, когда операция пытается получить доступ к данным за пределами допустимого диапазона.

## <a name="syntax"></a>Синтаксис

```cpp
public ref class OutOfBoundsException : COMException,    IException,    IPrintable,    IEquatable
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в описании класса [COMException](../cppcx/platform-comexception-class.md) .

### <a name="requirements"></a>Требования

**Минимальный поддерживаемый клиент:** Windows 8

**Минимальный поддерживаемый сервер:** Windows Server 2012

**Пространство имен:** Platform

**Метаданные:** platform.winmd

## <a name="see-also"></a>См. также

[Класс Platform::COMException](../cppcx/platform-comexception-class.md)