---
title: _getch, _getwch
ms.date: 11/04/2016
apiname:
- _getch
- _getwch
apilocation:
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
apitype: DLLExport
f1_keywords:
- getwch
- _getch
- _getwch
helpviewer_keywords:
- characters, getting from console
- getch function
- _getwch function
- console, reading from
- _getch function
- getwch function
ms.assetid: cc116be7-cff2-4274-970f-5e7b18ccc05c
ms.openlocfilehash: 0b8f8ed4985810526552a3b66e81462fd656bb23
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50666314"
---
# <a name="getch-getwch"></a>_getch, _getwch

Получает символ из консоли без отображения.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
int _getch( void );
wint_t _getwch( void );
```

## <a name="return-value"></a>Возвращаемое значение

Возвращает считанный символ. Ошибка не возвращается.

## <a name="remarks"></a>Примечания

**_Getch** и **_getwch** функции считывают один символ из консоли, но знак не. Эти функции нельзя использовать для считывания сочетания CTRL+C. При считывании функциональной клавиши или клавиши со стрелкой каждая из этих функций должна вызываться дважды. Первый вызов возвращает 0 или 0xE0, а второй вызов возвращает фактический код клавиши.

Эти функции блокируют вызывающий поток, поэтому они потокобезопасны. Описание неблокирующих версий см. в разделе [_getch_nolock, _getwch_nolock](getch-nolock-getwch-nolock.md).

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_gettch**|**_getch**|**_getch**|**_getwch**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_getch**|\<conio.h>|
|**_getwch**|\<conio.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_getch.c
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
      ch = _getch();
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
Type 'Y' when finished typing keys: Y
```

## <a name="see-also"></a>См. также

[Ввод-вывод на консоль и порт](../../c-runtime-library/console-and-port-i-o.md)<br/>
[_getche, _getwche](getche-getwche.md)<br/>
[_cgets, _cgetws](../../c-runtime-library/cgets-cgetws.md)<br/>
[getc, getwc](getc-getwc.md)<br/>
[_ungetch, _ungetwch, _ungetch_nolock, _ungetwch_nolock](ungetch-ungetwch-ungetch-nolock-ungetwch-nolock.md)<br/>
