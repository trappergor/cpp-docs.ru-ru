---
title: _com_error::ErrorInfo | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::ErrorInfo
dev_langs:
- C++
helpviewer_keywords:
- ErrorInfo method [C++]
ms.assetid: 071b446c-4395-4fb8-bd3d-300a8b25f5cd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1fc2906827e6a465106a3dbdcb8b63c7b53a39ee
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46039352"
---
# <a name="comerrorerrorinfo"></a>_com_error::ErrorInfo

**Блок, относящийся только к системам Microsoft**

Получает объект `IErrorInfo`, переданный конструктору.

## <a name="syntax"></a>Синтаксис

```
IErrorInfo * ErrorInfo( ) const throw( );
```

## <a name="return-value"></a>Возвращаемое значение

Необработанный элемент `IErrorInfo`, переданный в конструктор.

## <a name="remarks"></a>Примечания

Получает инкапсулированный `IErrorInfo` элемент `_com_error` объекта, или значение NULL, если нет `IErrorInfo` элемента записывается. Вызывающий объект должен вызвать `Release` для возвращенного объекта после завершения с помощью его.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Класс _com_error](../cpp/com-error-class.md)