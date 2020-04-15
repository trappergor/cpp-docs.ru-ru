---
title: _kbhit
ms.date: 4/2/2020
api_name:
- _kbhit
- _o__kbhit
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _kbhit
- conio/_kbhit
helpviewer_keywords:
- keyboard input
- user input, checking for keyboard
- kbhit function
- console
- console, checking
- keyboards, keyboard input
- _kbhit function
- keyboards, checking input
ms.assetid: e82a1cc9-bbec-4150-b678-a7e433220fe4
ms.openlocfilehash: c49a924a38aed3ff2d7953e150c4f3f1f3a5a25c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81342254"
---
# <a name="_kbhit"></a>_kbhit

Проверяет консоль на предмет ввода с клавиатуры.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C

int _kbhit( void );
```

## <a name="return-value"></a>Возвращаемое значение

**_kbhit** возвращает ненулевое значение, если ключ был нажат. В противном случае возвращается значение 0.

## <a name="remarks"></a>Remarks

**Функция _kbhit** проверяет консоль на наличие последнего нажатия клавиши. Если функция возвращает ненулевое значение, нажатие клавиши ожидает в буфере. Программа может позвонить **_getch** или **_getche,** чтобы получить нажатие клавиши.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_kbhit**|\<conio.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Пример

```C
// crt_kbhit.c
// compile with: /c
/* This program loops until the user
* presses a key. If _kbhit returns nonzero, a
* keystroke is waiting in the buffer. The program
* can call _getch or _getche to get the keystroke.
*/

#include <conio.h>
#include <stdio.h>

int main( void )
{
   /* Display message until key is pressed. */
   while( !_kbhit() )
      _cputs( "Hit me!! " );

   /* Use _getch to throw key away. */
   printf( "\nKey struck was '%c'\n", _getch() );
}
```

### <a name="sample-output"></a>Пример выходных данных

```Output
Hit me!! Hit me!! Hit me!! Hit me!! Hit me!! Hit me!! Hit me!!
Key struck was 'q'
```

## <a name="see-also"></a>См. также раздел

[Консоль и порт I/O](../../c-runtime-library/console-and-port-i-o.md)<br/>
