---
title: Event::operator =-оператор | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Event::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= operator
ms.assetid: d8fe9820-8856-4899-9553-56226bdc4945
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 072d4af94e4889d49d9b4876daa27cb4801d60d0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46447015"
---
# <a name="eventoperator-operator"></a>Оператор Event::operator=

Назначает указанное **событий** ссылку на текущий **событий** экземпляра.

## <a name="syntax"></a>Синтаксис

```cpp
WRL_NOTHROW Event& operator=(
   _Inout_ Event&& h
);
```

### <a name="parameters"></a>Параметры

*h*<br/>
Ссылка rvalue на **событий** экземпляра.

## <a name="return-value"></a>Возвращаемое значение

Указатель на текущий **событий** экземпляра.

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::wrl:: wrappers

## <a name="see-also"></a>См. также

[Класс Event (библиотека шаблонов C++ среды выполнения Windows)](../windows/event-class-windows-runtime-cpp-template-library.md)