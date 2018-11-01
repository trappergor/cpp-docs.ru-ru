---
title: _com_error::GUID
ms.date: 11/04/2016
f1_keywords:
- _com_error::GUID
helpviewer_keywords:
- GUID method [C++]
ms.assetid: e84c2c23-d02e-48f8-b776-9bd6937296d2
ms.openlocfilehash: 905b67577a65b81be0b4d18c7513652dd8c5f055
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50661634"
---
# <a name="comerrorguid"></a>_com_error::GUID

**Блок, относящийся только к системам Microsoft**

Вызывает функцию `IErrorInfo::GetGUID`.

## <a name="syntax"></a>Синтаксис

```
GUID GUID( ) const throw( );
```

## <a name="return-value"></a>Возвращаемое значение

Возвращает результат `IErrorInfo::GetGUID` для `IErrorInfo` записанного в `_com_error` объекта. Если не `IErrorInfo` записывается объект, он возвращает `GUID_NULL`.

## <a name="remarks"></a>Примечания

Любые сбои при вызове `IErrorInfo::GetGUID` метод игнорируется.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Класс _com_error](../cpp/com-error-class.md)