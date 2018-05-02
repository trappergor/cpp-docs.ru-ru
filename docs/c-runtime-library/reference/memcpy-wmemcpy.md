---
title: memcpy, wmemcpy | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
apitype: DLLExport
f1_keywords:
- wmemcpy
- memcpy
dev_langs:
- C++
helpviewer_keywords:
- wmemcpy function
- memcpy function
ms.assetid: 34abb90b-bffb-46dc-a2f3-a5e9940839d6
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a31ada40bfab599b6da41da268bf79792f8ebf20
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
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

**memcpy** копии *число* байтов из *src* для *dest*; **wmemcpy** копии *число* расширенных символов (два байта). Если источника и назначения перекрываются, то поведение **memcpy** не определено. Используйте **memmove** для обработки перекрывающихся областей.

> [!IMPORTANT]
> Убедитесь в том, что буфер назначения равен или превосходит по размеру исходный буфер. Дополнительные сведения см. в разделе [Как избежать переполнения буфера](http://msdn.microsoft.com/library/windows/desktop/ms717795).

> [!IMPORTANT]
> Так как так много переполнения буфера и таким образом потенциальной уязвимости безопасности, было связано с ненадлежащим использованием **memcpy**, эта функция будет включена в список «запрещенных» жизненного цикла разработки безопасности (SDL).  Можно заметить, что некоторые библиотечные классы VC ++ по-прежнему использовать **memcpy**.  Кроме того, можно заметить, что оптимизация компилятора VC ++ иногда также вызывает функцию **memcpy**.  Язык Visual C++ разрабатывался в соответствии с требованиями SDL, поэтому использование этой запрещенной функции тщательно анализировалось.  В случае использования в библиотеке вызовы были тщательно изучены на предмет того, не могут ли они вызвать переполнение буфера.  В случае с компилятором иногда некоторые шаблоны кода были признаны идентичными шаблону **memcpy**и поэтому заменены вызов функции.  В таких случаях использование **memcpy** — не более безопасно, чем исходный были бы инструкции; они просто оптимизированы для вызова оптимизировать производительность **memcpy** функции.  Точно так же, как использование "безопасных" функций CRT не гарантирует безопасности, использование "запрещенных" функций не обязательно приводит к опасным ситуациям (они просто требуют более внимательного подхода к обеспечению безопасности).
>
> Поскольку **memcpy** использования в компиляторе VC ++ и библиотеках было тщательно проанализировано, ее вызовы разрешены в коде, который в остальном соответствует процессу SDL.  **memcpy** вызовы в исходном коде приложений соответствуют только SDL, если они были проверены специалистами по безопасности.

**Memcpy** и **wmemcpy** функции будет прекращена, только если константа **_CRT_SECURE_DEPRECATE_MEMORY** определяется перед оператором включения в порядке для функции, не рекомендуется, например, в приведенном ниже примере:

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

В разделе [memmove](memmove-wmemmove.md) образец демонстрирует использование **memcpy**.

## <a name="see-also"></a>См. также

[Манипуляция буфером](../../c-runtime-library/buffer-manipulation.md)<br/>
[_memccpy](memccpy.md)<br/>
[memchr, wmemchr](memchr-wmemchr.md)<br/>
[memcmp, wmemcmp](memcmp-wmemcmp.md)<br/>
[memmove, wmemmove](memmove-wmemmove.md)<br/>
[memset, wmemset](memset-wmemset.md)<br/>
[strcpy_s, wcscpy_s, _mbscpy_s](strcpy-s-wcscpy-s-mbscpy-s.md)<br/>
[strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)<br/>
