---
title: _com_error::_com_error
ms.date: 11/04/2016
f1_keywords:
- _com_error::_com_error
helpviewer_keywords:
- _com_error method [C++]
ms.assetid: 0a69e46c-caab-49ef-b091-eee401253ce6
ms.openlocfilehash: 8856289605cce430fdab36d6e3e8b743190e02ea
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50631742"
---
# <a name="comerrorcomerror"></a>_com_error::_com_error

**Блок, относящийся только к системам Microsoft**

Создает **_com_error** объекта.

## <a name="syntax"></a>Синтаксис

```
_com_error(
   HRESULT hr,
   IErrorInfo* perrinfo = NULL,
   bool fAddRef=false) throw( );

_com_error( const _com_error& that ) throw( );
```

#### <a name="parameters"></a>Параметры

*hr*<br/>
Информация HRESULT.

*perrinfo*<br/>
Объект `IErrorInfo`.

*fAddRef*<br/>
Значение по умолчанию дает конструктору указание вызвать метод AddRef на отличный от null `IErrorInfo` интерфейс. Это обеспечивает правильный подсчет ссылок в общем случае, когда владение интерфейсом передается в **_com_error** объект, например:

```cpp
throw _com_error(hr, perrinfo);
```

Если вы не хотите код, чтобы передать права владения для **_com_error** объекта и `AddRef` необходим для смещения `Release` в **_com_error** деструктор, конструируется объект как выглядит следующим образом:

```cpp
_com_error err(hr, perrinfo, true);
```

*,*<br/>
Существующий **_com_error** объекта.

## <a name="remarks"></a>Примечания

Первый конструктор создает новый объект по заданному HRESULT и необязательный `IErrorInfo` объекта. Второй создает копию существующего **_com_error** объекта.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Класс _com_error](../cpp/com-error-class.md)