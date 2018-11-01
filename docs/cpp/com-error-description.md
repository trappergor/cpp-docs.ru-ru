---
title: _com_error::Description
ms.date: 11/04/2016
f1_keywords:
- _com_error::Description
helpviewer_keywords:
- Description method [C++]
ms.assetid: 88191e24-4ee8-44a6-8c4c-3758e22e0548
ms.openlocfilehash: a517c40e9adfbda2d790ce41a48ccf8658bcd3e0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50544395"
---
# <a name="comerrordescription"></a>_com_error::Description

**Блок, относящийся только к системам Microsoft**

Вызывает функцию `IErrorInfo::GetDescription`.

## <a name="syntax"></a>Синтаксис

```
_bstr_t Description( ) const;
```

## <a name="return-value"></a>Возвращаемое значение

Возвращает результат `IErrorInfo::GetDescription` для `IErrorInfo` записанного в `_com_error` объекта. Результирующая функция `BSTR` инкапсулируется в объект `_bstr_t`. Если не `IErrorInfo` будет записан, возвращается пустой `_bstr_t`.

## <a name="remarks"></a>Примечания

Вызовы `IErrorInfo::GetDescription` и возвращает функцию `IErrorInfo` записанного в `_com_error` объекта. Любые сбои при вызове `IErrorInfo::GetDescription` метод игнорируется.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Класс _com_error](../cpp/com-error-class.md)