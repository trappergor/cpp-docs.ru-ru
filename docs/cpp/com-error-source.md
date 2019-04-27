---
title: _com_error::Source
ms.date: 11/04/2016
f1_keywords:
- _com_error::Source
helpviewer_keywords:
- Source method [C++]
ms.assetid: 55353741-fabc-4b0c-9787-b5a69bb189f2
ms.openlocfilehash: 682070877f269967405677d027b20707c8366f61
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62154965"
---
# <a name="comerrorsource"></a>_com_error::Source

**Блок, относящийся только к системам Microsoft**

Вызывает функцию `IErrorInfo::GetSource`.

## <a name="syntax"></a>Синтаксис

```
_bstr_t Source() const;
```

## <a name="return-value"></a>Возвращаемое значение

Возвращает результат `IErrorInfo::GetSource` для `IErrorInfo` записанного в `_com_error` объекта. Результирующая функция `BSTR` инкапсулируется в объект `_bstr_t`. Если не `IErrorInfo` будет записан, возвращается пустой `_bstr_t`.

## <a name="remarks"></a>Примечания

Любые сбои при вызове `IErrorInfo::GetSource` метод игнорируется.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Класс _com_error](../cpp/com-error-class.md)