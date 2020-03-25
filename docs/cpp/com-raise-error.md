---
title: _com_raise_error
ms.date: 11/04/2016
f1_keywords:
- _com_raise_error
helpviewer_keywords:
- _com_raise_error function
ms.assetid: a98226c2-c3fe-44f1-8ff5-85863de11cd6
ms.openlocfilehash: 2012ec98d8d40d60a7f12feb68bdc371e1616223
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80189797"
---
# <a name="_com_raise_error"></a>_com_raise_error

**Блок, относящийся только к системам Microsoft**

Вызывает исключение [_com_error](../cpp/com-error-class.md) в ответ на сбой.

## <a name="syntax"></a>Синтаксис

```
void __stdcall _com_raise_error(
   HRESULT hr,
   IErrorInfo* perrinfo = 0
);
```

#### <a name="parameters"></a>Параметры

*кадров*<br/>
Сведения HRESULT.

*перринфо*<br/>
Объект `IErrorInfo`.

## <a name="remarks"></a>Remarks

**_com_raise_error**, который определен в \<comdef. h >, может быть заменен на написанную пользователем версию с тем же именем и прототипом. Это можно сделать, если требуется использовать `#import` без обработки исключений C++. В этом случае пользовательская версия **_com_raise_error** может решить выполнить `longjmp` или отобразить окно сообщения и остановить. Однако пользовательская версия не должна возвращаться, поскольку код поддержки COM в компиляторе не ожидает ее возврата.

Можно также использовать [_set_com_error_handler](../cpp/set-com-error-handler.md) для замены функции обработки ошибок по умолчанию.

По умолчанию **_com_raise_error** определяется следующим образом:

```cpp
void __stdcall _com_raise_error(HRESULT hr, IErrorInfo* perrinfo) {
   throw _com_error(hr, perrinfo);
}
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="requirements"></a>Требования

**Заголовок:** \<comdef. h >

**Библиотека:** Если wchar_t является параметром компилятора **native Type** , используется комсуппв. lib или комсуппвд. lib. Если **wchar_t имеет собственный тип** , то используйте комсупп. lib. Дополнительные сведения см. в разделе [/Zc:wchar_t (wchar_t — это собственный тип)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md).

## <a name="see-also"></a>См. также раздел

[Глобальные функции COM-модели компилятора](../cpp/compiler-com-global-functions.md)<br/>
[_set_com_error_handler](../cpp/set-com-error-handler.md)
