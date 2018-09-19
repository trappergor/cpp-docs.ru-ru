---
title: _com_error::Description | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::Description
dev_langs:
- C++
helpviewer_keywords:
- Description method [C++]
ms.assetid: 88191e24-4ee8-44a6-8c4c-3758e22e0548
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 90208866ee08d6990d8f1b5322a38fbd2d63a651
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46091794"
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