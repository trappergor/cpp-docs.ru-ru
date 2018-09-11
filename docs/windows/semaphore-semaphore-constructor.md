---
title: Конструктор Semaphore::Semaphore | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::Semaphore
dev_langs:
- C++
helpviewer_keywords:
- Semaphore, constructor
ms.assetid: 91c22ae7-181e-460d-ad40-70c3a53b26fd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a585f052c42453f0eb9fe8a39a21a5561d4b00c3
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42598964"
---
# <a name="semaphoresemaphore-constructor"></a>Конструктор Semaphore::Semaphore

Инициализирует новый экземпляр класса **семафора** класса.

## <a name="syntax"></a>Синтаксис

```cpp
explicit Semaphore(
   HANDLE h
);

WRL_NOTHROW Semaphore(
   _Inout_ Semaphore&& h
);
```

### <a name="parameters"></a>Параметры

*h*  
Дескриптор или rvalue ссылка для **семафора** объекта.

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::wrl:: wrappers

## <a name="see-also"></a>См. также
[Класс Semaphore](../windows/semaphore-class.md)