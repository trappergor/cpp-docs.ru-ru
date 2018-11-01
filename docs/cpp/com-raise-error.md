---
title: _com_raise_error
ms.date: 11/04/2016
f1_keywords:
- _com_raise_error
helpviewer_keywords:
- _com_raise_error function
ms.assetid: a98226c2-c3fe-44f1-8ff5-85863de11cd6
ms.openlocfilehash: 5790fceef26d6de4edff604270cc7108f764aced
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50627569"
---
# <a name="comraiseerror"></a>_com_raise_error

**Блок, относящийся только к системам Microsoft**

Создает [_com_error](../cpp/com-error-class.md) в ответ на сбой.

## <a name="syntax"></a>Синтаксис

```
void __stdcall _com_raise_error(
   HRESULT hr,
   IErrorInfo* perrinfo = 0
);
```

#### <a name="parameters"></a>Параметры

*hr*<br/>
Информация HRESULT.

*perrinfo*<br/>
Объект `IErrorInfo`.

## <a name="remarks"></a>Примечания

**_com_raise_error**, который определен в \<comdef.h >, могут быть заменены версии одним и тем же именем и прототипом, написанный пользователем. Это можно сделать, если требуется использовать `#import` без обработки исключений C++. В этом случае пользовательская версия **_com_raise_error** может решить выполнить `longjmp` или отобразить окно сообщения и остановки. Однако пользовательская версия не должна возвращаться, поскольку код поддержки COM в компиляторе не ожидает ее возврата.

Можно также использовать [_set_com_error_handler](../cpp/set-com-error-handler.md) для замены функции обработки ошибок по умолчанию.

По умолчанию **_com_raise_error** определяется следующим образом:

```cpp
void __stdcall _com_raise_error(HRESULT hr, IErrorInfo* perrinfo) {
   throw _com_error(hr, perrinfo);
}
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="requirements"></a>Требования

**Заголовок:** \<comdef.h >

**LIB:** Если **wchar_t — собственный тип** включен параметр компилятора, используйте comsuppw.lib или comsuppwd.lib. Если **wchar_t — собственный тип** отключен, используйте comsupp.lib. Дополнительные сведения см. в разделе [/Zc:wchar_t (wchar_t — это собственный тип)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md).

## <a name="see-also"></a>См. также

[Глобальные функции COM-модели компилятора](../cpp/compiler-com-global-functions.md)<br/>
[_set_com_error_handler](../cpp/set-com-error-handler.md)