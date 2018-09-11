---
title: Класс Platform::WrongThreadException | Документация Майкрософт
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::WrongThreadException
- VCCORLIB/Platform::WrongThreadException::WrongThreadException
dev_langs:
- C++
helpviewer_keywords:
- Platform::WrongThreadException
ms.assetid: c193f97e-0392-4535-a4c4-0711e4e4a836
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1fe772f1c2925ce28d0e445023ab14d82b9b3f23
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44107696"
---
# <a name="platformwrongthreadexception-class"></a>Класс Platform::WrongThreadException

Вызывается, если поток выполняет вызов посредством указателя на интерфейс для прокси-объекта, который не принадлежит подразделению потока.

## <a name="syntax"></a>Синтаксис

```cpp
public ref class WrongThreadException : COMException,    IException,    IPrintable,    IEquatable
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в описании класса [COMException](../cppcx/platform-comexception-class.md).

### <a name="requirements"></a>Требования

**Минимальный поддерживаемый клиент:** Windows 8

**Минимальный поддерживаемый сервер:** Windows Server 2012

**Пространство имен:** Platform

**Метаданные:** platform.winmd

## <a name="see-also"></a>См. также

[Класс Platform::COMException](../cppcx/platform-comexception-class.md)