---
title: _com_error::ErrorMessage
ms.date: 11/04/2016
f1_keywords:
- _com_error::ErrorMessage
helpviewer_keywords:
- ErrorMessage method [C++]
ms.assetid: e47335b6-01af-4975-a841-121597479eb7
ms.openlocfilehash: b1c1b5a79cdf5ee2a4a17d969d23ce0d0d85ab54
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155186"
---
# <a name="comerrorerrormessage"></a>_com_error::ErrorMessage

**Блок, относящийся только к системам Microsoft**

Получает строковое сообщение для значения HRESULT, хранящегося в объекте `_com_error`.

## <a name="syntax"></a>Синтаксис

```
const TCHAR * ErrorMessage( ) const throw( );
```

## <a name="return-value"></a>Возвращаемое значение

Возвращает строковое сообщение для HRESULT записанного в `_com_error` объекта. Если значение HRESULT равно сопоставлен 16-битный [wCode](../cpp/com-error-wcode.md), универсальное сообщение "`IDispatch error #<wCode>`" возвращается. Если сообщение не найдено, возвращается универсальное сообщение "`Unknown error #<hresult>`". Возвращаемая строка является Юникода или многобайтовая строка, в зависимости от состояния макроса _UNICODE.

## <a name="remarks"></a>Примечания

Извлекает соответствующий текст системного сообщения для HRESULT записанного в `_com_error` объекта. Текст системного сообщения получается путем вызова Win32 [FormatMessage](/windows/desktop/api/winbase/nf-winbase-formatmessage) функции. Возвращаемая строка выделяется API `FormatMessage`; эта строка освобождается при уничтожении объекта `_com_error`.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Класс _com_error](../cpp/com-error-class.md)