---
title: _com_error::HelpContext
ms.date: 11/04/2016
f1_keywords:
- _com_error::HelpContext
helpviewer_keywords:
- HelpContext method [C++]
ms.assetid: 160d6443-9b68-4cf5-a540-50da951a5b2b
ms.openlocfilehash: a421a7fd7fa0817c74dac66946e28928b2ad82dc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155089"
---
# <a name="comerrorhelpcontext"></a>_com_error::HelpContext

**Блок, относящийся только к системам Microsoft**

Вызывает функцию `IErrorInfo::GetHelpContext`.

## <a name="syntax"></a>Синтаксис

```
DWORD HelpContext( ) const throw( );
```

## <a name="return-value"></a>Возвращаемое значение

Возвращает результат `IErrorInfo::GetHelpContext` для `IErrorInfo` записанного в `_com_error` объекта. Если нет `IErrorInfo` объекта записан, возвращается нулевое значение.

## <a name="remarks"></a>Примечания

Любые сбои при вызове `IErrorInfo::GetHelpContext` метод игнорируется.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Класс _com_error](../cpp/com-error-class.md)