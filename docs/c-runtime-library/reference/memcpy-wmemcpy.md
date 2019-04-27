---
title: memcpy, wmemcpy
ms.date: 11/04/2016
apiname:
- memcpy
- wmemcpy
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
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- wmemcpy
- memcpy
helpviewer_keywords:
- wmemcpy function
- memcpy function
ms.assetid: 34abb90b-bffb-46dc-a2f3-a5e9940839d6
ms.openlocfilehash: afdb854bd28b55735cc6b5e26788307e2db0caa6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62156594"
---
# <a name="memcpy-wmemcpy"></a>memcpy, wmemcpy

Копирует байты между буферами. Существуют более безопасные версии этих функций; см. раздел [memcpy_s, wmemcpy_s](memcpy-s-wmemcpy-s.md).

## <a name="syntax"></a>Синтаксис

```C
void *memcpy(
   void *dest,
   const void *src,
   size_t count
);
wchar_t *wmemcpy(
   wchar_t *dest,
   const wchar_t *src,
   size_t count
);
```

### <a name="parameters"></a>Параметры

*dest*<br/>
Новый буфер.

*src*<br/>
Буфер, из которого происходит копирование.

*count*<br/>
Число копируемых символов.

## <a name="return-value"></a>Возвращаемое значение

Значение *dest*.

## <a name="remarks"></a>Примечания

**memcpy** копий *число* байтов из *src* для *dest*; **wmemcpy** копий *число* расширенных символов (два байта). Если источника и назначения перекрываются, поведение **memcpy** не определено. Используйте **memmove** для обработки перекрывающихся областей.

> [!IMPORTANT]
> Убедитесь в том, что буфер назначения равен или превосходит по размеру исходный буфер. Дополнительные сведения см. в разделе [Как избежать переполнения буфера](/windows/desktop/SecBP/avoiding-buffer-overruns).

> [!IMPORTANT]
> Так как так много переполнения буфера и таким образом потенциальной уязвимости безопасности, было связано с ненадлежащим использованием из **memcpy**, эта функция включена в список «запрещенных» функций, Security Development Lifecycle (SDL).  Вы можете заметить, что некоторые библиотечные классы VC ++ по-прежнему использовать **memcpy**.  Кроме того, вы можете заметить, что оптимизатор компилятора VC ++ иногда создает вызовы **memcpy**.  Язык Visual C++ разрабатывался в соответствии с требованиями SDL, поэтому использование этой запрещенной функции тщательно анализировалось.  В случае использования в библиотеке вызовы были тщательно изучены на предмет того, не могут ли они вызвать переполнение буфера.  В случае с компилятором, иногда некоторые шаблоны кода распознаются идентичными шаблону **memcpy**и поэтому заменены вызова функции.  В таких случаях использование **memcpy** — не более предпочтительным, чем использование исходных инструкций; они просто оптимизированы для вызова в плане производительности **memcpy** функции.  Точно так же, как использование "безопасных" функций CRT не гарантирует безопасности, использование "запрещенных" функций не обязательно приводит к опасным ситуациям (они просто требуют более внимательного подхода к обеспечению безопасности).
>
> Так как **memcpy** использования компилятора VC ++ и библиотеками было тщательно проанализировано, ее вызовы разрешены в коде, в противном случае соответствующий SDL.  **memcpy** вызовы, представленные в исходный код приложения совместимы только с SDL при этом были проверены специалистами по безопасности.

**Memcpy** и **wmemcpy** функции станут устаревшими, только если константа **_CRT_SECURE_DEPRECATE_MEMORY** определяется перед оператором включения выполнился функции, не рекомендуется, как показано в примере ниже:

```C
#define _CRT_SECURE_DEPRECATE_MEMORY
#include <memory.h>
```

или

```C
#define _CRT_SECURE_DEPRECATE_MEMORY
#include <wchar.h>
```

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**memcpy**|\<memory.h> или \<string.h>|
|**wmemcpy**|\<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. в разделе [memmove](memmove-wmemmove.md) пример демонстрирует использование **memcpy**.

## <a name="see-also"></a>См. также

[Манипуляция буфером](../../c-runtime-library/buffer-manipulation.md)<br/>
[_memccpy](memccpy.md)<br/>
[memchr, wmemchr](memchr-wmemchr.md)<br/>
[memcmp, wmemcmp](memcmp-wmemcmp.md)<br/>
[memmove, wmemmove](memmove-wmemmove.md)<br/>
[memset, wmemset](memset-wmemset.md)<br/>
[strcpy_s, wcscpy_s, _mbscpy_s](strcpy-s-wcscpy-s-mbscpy-s.md)<br/>
[strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)<br/>
