---
title: _getche, _getwche
ms.date: 4/2/2020
api_name:
- _getwche
- _getche
- _o__getche
- _o__getwche
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
- api-ms-win-crt-conio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- getwche
- _getche
- _getwche
helpviewer_keywords:
- characters, getting from console
- _getwche function
- getche function
- console, reading from
- getwche function
- _getche function
ms.assetid: eac978a8-c43a-4130-938f-54f12e2a0fda
ms.openlocfilehash: 59af5360ed8d966629d5e46f77681631a521d502
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81344541"
---
# <a name="_getche-_getwche"></a>_getche, _getwche

Получает символ из консоли с отображением.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
int _getche( void );
wint_t _getwche( void );
```

## <a name="return-value"></a>Возвращаемое значение

Возвращает считанный символ. Ошибка не возвращается.

## <a name="remarks"></a>Remarks

**Функции _getche** и **_getwche** считывали один символ с помощью эха, что означает, что символ отображается на консоли. Эти функции нельзя использовать для считывания сочетания CTRL+C. При считывании функциональной клавиши или клавиши со стрелкой каждая из этих функций должна вызываться дважды. Первый вызов возвращает 0 или 0xE0, а второй вызов возвращает фактический код клавиши.

Эти функции блокируют вызывающий поток, поэтому они потокобезопасны. Описание неблокирующих версий см. в разделе [_getche_nolock, _getwche_nolock](getche-nolock-getwche-nolock.md).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_getche**|**_getche**|**_getch**|**_getwche**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_getche**|\<conio.h>|
|**_getwche**|\<conio.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_getche.c
// compile with: /c
// This program reads characters from
// the keyboard until it receives a 'Y' or 'y'.

#include <conio.h>
#include <ctype.h>

int main( void )
{
   int ch;

   _cputs( "Type 'Y' when finished typing keys: " );
   do
   {
      ch = _getche();
      ch = toupper( ch );
   } while( ch != 'Y' );

   _putch( ch );
   _putch( '\r' );    // Carriage return
   _putch( '\n' );    // Line feed
}
```

```Input
abcdefy
```

```Output
Type 'Y' when finished typing keys: abcdefyY
```

## <a name="see-also"></a>См. также раздел

[Консоль и порт I/O](../../c-runtime-library/console-and-port-i-o.md)<br/>
[_cgets, _cgetws](../../c-runtime-library/cgets-cgetws.md)<br/>
[getc, getwc](getc-getwc.md)<br/>
[_ungetch, _ungetwch, _ungetch_nolock, _ungetwch_nolock](ungetch-ungetwch-ungetch-nolock-ungetwch-nolock.md)<br/>
