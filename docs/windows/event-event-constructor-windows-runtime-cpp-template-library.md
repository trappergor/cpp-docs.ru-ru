---
title: Конструктор Event::Event (библиотека шаблонов C++ среды выполнения Windows) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Event::Event
dev_langs:
- C++
ms.assetid: 21495297-9612-4095-9256-16e168cc0021
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8bd9f02935d0d88976fd3b62c7276f106519fa74
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46381014"
---
# <a name="eventevent-constructor-windows-runtime-c-template-library"></a>Конструктор Event::Event (библиотека шаблонов C++ среды выполнения Windows)

Инициализирует новый экземпляр класса **событий** класса.

## <a name="syntax"></a>Синтаксис

```cpp
explicit Event(
   HANDLE h = HandleT::Traits::GetInvalidValue()  
);
WRL_NOTHROW Event(
   _Inout_ Event&& h
);
```

### <a name="parameters"></a>Параметры

*h*<br/>
Дескриптор события. По умолчанию *h* инициализируется **nullptr**.

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::wrl:: wrappers

## <a name="see-also"></a>См. также

[Класс Event (библиотека шаблонов C++ среды выполнения Windows)](../windows/event-class-windows-runtime-cpp-template-library.md)