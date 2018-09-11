---
title: Конструктор InvokeHelper::InvokeHelper | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::InvokeHelper::InvokeHelper
dev_langs:
- C++
helpviewer_keywords:
- InvokeHelper, constructor
ms.assetid: 0223c574-abc3-4fc0-99e6-38626ba79243
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1ad09a5a4794a9db8882a088f90da5046b6f7b9d
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42609244"
---
# <a name="invokehelperinvokehelper-constructor"></a>Конструктор InvokeHelper::InvokeHelper

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
explicit InvokeHelper(
   TCallback callback
);
```

### <a name="parameters"></a>Параметры

*обратный вызов*  
Обработчик событий.

## <a name="remarks"></a>Примечания

Инициализирует новый экземпляр класса **InvokeHelper** класса.

`TCallback` Параметр шаблона тип обработчика событий.

## <a name="requirements"></a>Требования

**Заголовок:** event.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="see-also"></a>См. также

[Структура InvokeHelper](../windows/invokehelper-structure.md)  
[Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)