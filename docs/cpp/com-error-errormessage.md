---
title: _com_error::ErrorMessage
ms.date: 11/04/2016
f1_keywords:
- _com_error::ErrorMessage
helpviewer_keywords:
- ErrorMessage method [C++]
ms.assetid: e47335b6-01af-4975-a841-121597479eb7
ms.openlocfilehash: 44fc9755cd69050ea82145636f01614258943794
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69500583"
---
# <a name="_com_errorerrormessage"></a>_com_error::ErrorMessage

**Блок, относящийся только к системам Microsoft**

Получает строковое сообщение для значения HRESULT, хранящегося в объекте `_com_error`.

## <a name="syntax"></a>Синтаксис

```
const TCHAR * ErrorMessage( ) const throw( );
```

## <a name="return-value"></a>Возвращаемое значение

Возвращает строковое сообщение для HRESULT, записанного в `_com_error` объекте. Если HRESULT является сопоставленным 16-битным [wCode](../cpp/com-error-wcode.md), возвращается универсальное сообщение "`IDispatch error #<wCode>`". Если сообщение не найдено, возвращается универсальное сообщение "`Unknown error #<hresult>`". Возвращаемая строка может быть строкой в Юникоде или многобайтовой кодировкой в зависимости от состояния макроса _UNICODE.

## <a name="remarks"></a>Примечания

Извлекает соответствующий текст системного сообщения для HRESULT, `_com_error` записанного в объекте. Текст системного сообщения получается путем вызова функции "Win32 [FormatMessage](/windows/win32/api/winbase/nf-winbase-formatmessage) ". Возвращаемая строка выделяется API `FormatMessage`; эта строка освобождается при уничтожении объекта `_com_error`.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Класс _com_error](../cpp/com-error-class.md)