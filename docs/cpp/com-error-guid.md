---
title: _com_error::GUID | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::GUID
dev_langs:
- C++
helpviewer_keywords:
- GUID method [C++]
ms.assetid: e84c2c23-d02e-48f8-b776-9bd6937296d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f63d81fa8550bd9cbb7c051803c0d1e891cefe15
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46031062"
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