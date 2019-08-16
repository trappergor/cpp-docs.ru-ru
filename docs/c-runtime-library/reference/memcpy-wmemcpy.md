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
ms.openlocfilehash: f687e231060c287e206017dc61fe1d5193d8f0de
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69499635"
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

**memcpy** копирует *число* байтов из *src* в *dest*; **wmemcpy** копирует символы расширенного *числа* (2 байта). Если источник и назначение перекрываются, поведение **memcpy** не определено. Используйте **memmove** для управления перекрывающимися областями.

> [!IMPORTANT]
> Убедитесь в том, что буфер назначения равен или превосходит по размеру исходный буфер. Дополнительные сведения см. в разделе [Как избежать переполнения буфера](/windows/win32/SecBP/avoiding-buffer-overruns).

> [!IMPORTANT]
> Так как большое количество переполнений буфера и, таким образом, потенциальные эксплойты безопасности, отслеживаются в неправильном использовании **memcpy**, эта функция указана между "запрещенными" функциями жизненного цикла разработки безопасности (SDL).  Можно заметить, что некоторые классы библиотек VC + + продолжают использовать **memcpy**.  Кроме того, можно заметить, что оптимизатор компилятора VC + + иногда создает вызовы **memcpy**.  Язык Visual C++ разрабатывался в соответствии с требованиями SDL, поэтому использование этой запрещенной функции тщательно анализировалось.  В случае использования в библиотеке вызовы были тщательно изучены на предмет того, не могут ли они вызвать переполнение буфера.  В случае компилятора иногда определенные шаблоны кода распознаются как идентичные шаблону **memcpy**и, таким образом, заменяются вызовом функции.  В таких случаях использование **memcpy** является более ненадежным по сравнению с исходными инструкциями. они просто оптимизированы для вызова функции **memcpy** , настроенной для производительности.  Точно так же, как использование "безопасных" функций CRT не гарантирует безопасности, использование "запрещенных" функций не обязательно приводит к опасным ситуациям (они просто требуют более внимательного подхода к обеспечению безопасности).
>
> Поскольку использование **memcpy** компилятором и библиотеками VC + + было тщательно изучены, эти вызовы разрешены в коде, который в противном случае соответствует SDL.  вызовы **memcpy** , появившиеся в исходном коде приложения, соответствуют требованиям SDL, только если они были проверены экспертами по безопасности.

Функции **memcpy** и **wmemcpy** будут считаться устаревшими только в том случае, если константа **_CRT_SECURE_DEPRECATE_MEMORY** определена до оператора включения, чтобы функции были устаревшими, например, в примере ниже:

```C
#define _CRT_SECURE_DEPRECATE_MEMORY
#include <memory.h>
```

или диспетчер конфигурации служб

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

Пример использования **memcpy**см. в разделе [memmove](memmove-wmemmove.md) .

## <a name="see-also"></a>См. также

[Манипуляция буфером](../../c-runtime-library/buffer-manipulation.md)<br/>
[_memccpy](memccpy.md)<br/>
[memchr, wmemchr](memchr-wmemchr.md)<br/>
[memcmp, wmemcmp](memcmp-wmemcmp.md)<br/>
[memmove, wmemmove](memmove-wmemmove.md)<br/>
[memset, wmemset](memset-wmemset.md)<br/>
[strcpy_s, wcscpy_s, _mbscpy_s](strcpy-s-wcscpy-s-mbscpy-s.md)<br/>
[strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)<br/>
