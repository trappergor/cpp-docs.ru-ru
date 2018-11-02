---
title: _com_error::ErrorInfo
ms.date: 11/04/2016
f1_keywords:
- _com_error::ErrorInfo
helpviewer_keywords:
- ErrorInfo method [C++]
ms.assetid: 071b446c-4395-4fb8-bd3d-300a8b25f5cd
ms.openlocfilehash: 59ada8a7e098e57cca5641a439365851bbae2485
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50559007"
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