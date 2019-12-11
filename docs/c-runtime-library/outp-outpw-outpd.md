---
title: ыходной, аутпв, _outp, _outpw, _outpd
description: Описание устаревших и удаленных функций ыходной, аутпв, _outp, _outpw и _outpd библиотеки времени выполнения Microsoft C (CRT).
ms.date: 12/09/2019
api_name:
- _outpd
- _outp
- _outpw
- outp
- outpw
api_location:
- msvcrt.dll
- msvcr100.dll
- msvcr120.dll
- msvcr90.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr80.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _outpw
- _outpd
- _outp
- outp
- outpw
- outpd
helpviewer_keywords:
- outpw function
- words
- _outpd function
- outpd function
- outp function
- ports, writing bytes at
- bytes, writing to ports
- words, writing to ports
- double words
- double words, writing to ports
- _outpw function
- _outp function
ms.assetid: c200fe22-41f6-46fd-b0be-ebb805b35181
ms.openlocfilehash: 03d3df0bae9c2fa3cdd107f3c0de65105077c401
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988373"
---
# <a name="outp-outpw-_outp-_outpw-_outpd"></a>ыходной, аутпв, _outp, _outpw, _outpd

Выходные данные, в порте, байт (`outp`, `_outp`), слово (`outpw`, `_outpw`) или двойное слово (`_outpd`).

> [!IMPORTANT]
> Эти функции устарели. Начиная с Visual Studio 2015 они недоступны в CRT.  
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```cpp
int _outp(
   unsigned short port,
   int databyte
);
unsigned short _outpw(
   unsigned short port,
   unsigned short dataword
);
unsigned long _outpd(
   unsigned short port,
   unsigned long dataword
);
```

### <a name="parameters"></a>Параметры

\ *порта*
Номер порта.

*Byte,* \ "слово"
Выходные значения.

## <a name="return-value"></a>Возвращаемое значение

Функции возвращают выходные данные. Ошибка не возвращается.

## <a name="remarks"></a>Заметки

Функции `_outp`, `_outpw`и `_outpd` пишут байт, слово и двойное слово, соответственно, на указанный порт вывода. Аргумент *port* может быть любым целым числом без знака в диапазоне от 0 до 65535; *databyte* может быть любым целым числом в диапазоне от 0 до 255; *dataword* может быть любым значением в диапазоне целого числа, короткого целого без знака и длинного целого без знака, соответственно.

Поскольку эти функции пишут непосредственно на порт ввода-вывода, они не могут использоваться в пользовательском коде. Для получения дополнительных сведений об использовании портов ввода-вывода в этих операционных системах, выполните поиск по запросу "Последовательная связь в Win32" в MSDN.

Имена `outp` и `outpw` являются устаревшими, нерекомендуемыми именами для функций `_outp` и `_outpw`. Дополнительные сведения см. в разделе [имена функций POSIX](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|`_outp`|\<conio.h>|
|`_outpw`|\<conio.h>|
|`_outpd`|\<conio.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Все версии [библиотек времени выполнения языка C](../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>См. также:

[Ввод-вывод на консоль и порт](../c-runtime-library/console-and-port-i-o.md)\
[InP, инпв, _inp, _inpw, _inpd](../c-runtime-library/inp-inpw-inpd.md)
