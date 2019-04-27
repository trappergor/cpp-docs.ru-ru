---
title: _com_error::HelpFile
ms.date: 11/04/2016
f1_keywords:
- _com_error::HelpFile
helpviewer_keywords:
- HelpFile method [C++]
ms.assetid: d2d3a0a1-6b62-4d52-a818-3cfae545a4af
ms.openlocfilehash: 826ac53f001355127f16b7ad2a7583a0f8800de7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155037"
---
# <a name="comerrorhelpfile"></a>_com_error::HelpFile

**Блок, относящийся только к системам Microsoft**

Вызывает функцию `IErrorInfo::GetHelpFile`.

## <a name="syntax"></a>Синтаксис

```
_bstr_t HelpFile() const;
```

## <a name="return-value"></a>Возвращаемое значение

Возвращает результат `IErrorInfo::GetHelpFile` для `IErrorInfo` записанного в `_com_error` объекта. Результирующая строка BSTR инкапсулируется в объект `_bstr_t`. Если не `IErrorInfo` будет записан, возвращается пустой `_bstr_t`.

## <a name="remarks"></a>Примечания

Любые сбои при вызове `IErrorInfo::GetHelpFile` метод игнорируется.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Класс _com_error](../cpp/com-error-class.md)