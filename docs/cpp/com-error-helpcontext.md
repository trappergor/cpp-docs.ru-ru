---
title: _com_error::HelpContext | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::HelpContext
dev_langs:
- C++
helpviewer_keywords:
- HelpContext method [C++]
ms.assetid: 160d6443-9b68-4cf5-a540-50da951a5b2b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4c2a1810410194f1261da907199a3b6665e5be30
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46074374"
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