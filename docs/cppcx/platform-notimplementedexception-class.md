---
title: Класс Platform::NotImplementedException | Документация Майкрософт
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::NotImplementedException
- VCCORLIB/Platform::NotImplementedException::NotImplementedException
dev_langs:
- C++
helpviewer_keywords:
- Platform::NotImplementedException
ms.assetid: 6da26cc2-dde8-4aea-aa85-67aac55cf97b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8ac52615a9cc00a3fbfdb253e44c7ce5d239009a
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44103691"
---
# <a name="platformnotimplementedexception-class"></a>Класс Platform::NotImplementedException

Вызывается, если член интерфейса не реализован в производном типе.

## <a name="syntax"></a>Синтаксис

```cpp
public ref class NotImplementedException : COMException,    IException,    IPrintable,    IEquatable
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