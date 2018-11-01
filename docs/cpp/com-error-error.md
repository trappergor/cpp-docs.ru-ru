---
title: _com_error::Error
ms.date: 11/04/2016
f1_keywords:
- _com_error::Error
- Error
helpviewer_keywords:
- Error method [C++]
ms.assetid: b53a15fd-198e-4276-afcd-13439c4807f7
ms.openlocfilehash: 606f553060e71ece18b3d48159ec40133be28965
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50465472"
---
# <a name="comerrorerror"></a>_com_error::Error

**Блок, относящийся только к системам Microsoft**

Возвращает значение HRESULT, переданный в конструктор.

## <a name="syntax"></a>Синтаксис

```
HRESULT Error( ) const throw( );
```

## <a name="return-value"></a>Возвращаемое значение

Необработанный элемент HRESULT, переданный в конструктор.

## <a name="remarks"></a>Примечания

Получает инкапсулированный элемент HRESULT в `_com_error` объекта.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Класс _com_error](../cpp/com-error-class.md)