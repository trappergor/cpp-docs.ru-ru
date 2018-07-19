---
title: memcpy_s, wmemcpy_s | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- memcpy_s
- wmemcpy_s
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- wmemcpy_s
- memcpy_s
dev_langs:
- C++
helpviewer_keywords:
- memcpy_s function
- wmemcpy_s function
ms.assetid: 5504e20a-83d9-4063-91fc-3f55f7dabe99
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 12bf97e596a7cb4e3befa4c0633a8ef2df29a6d1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32403798"
---
# <a name="memcpys-wmemcpys"></a>memcpy_s, wmemcpy_s

Копирует байты между буферами. Это версии функций [memcpy, wmemcpy](memcpy-wmemcpy.md) с усовершенствованной безопасностью, как описано в разделе [Усовершенствования безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Синтаксис

```C
errno_t memcpy_s(
   void *dest,
   size_t destSize,
   const void *src,
   size_t count
);
errno_t wmemcpy_s(
   wchar_t *dest,
   size_t destSize,
   const wchar_t *src,
   size_t count
);
```

### <a name="parameters"></a>Параметры

*dest*<br/>
Новый буфер.

*destSize*<br/>
Размер буфера назначения в байтах для функции memcpy_s и в расширенных символах (wchar_t) для wmemcpy_s.

*src*<br/>
Буфер, из которого происходит копирование.

*count*<br/>
Число копируемых символов.

## <a name="return-value"></a>Возвращаемое значение

Возвращает нуль в случае успеха или код ошибки в случае неудачи.

### <a name="error-conditions"></a>Условия ошибок

|*dest*|*destSize*|*src*|*count*|Возвращаемое значение|Содержимое *dest*|
|------------|----------------|-----------|---|------------------|------------------------|
|any|any|any|0|0|Без изменений|
|**NULL**|any|any|ненулевое значение|**EINVAL**|Без изменений|
|any|any|**NULL**|ненулевое значение|**EINVAL**|*dest* обнуляется|
|any|< *Счетчик*|any|ненулевое значение|**ERANGE**|*dest* обнуляется|

## <a name="remarks"></a>Примечания

**memcpy_s** копии *число* байтов из *src* для *dest*; **wmemcpy_s** копии *число* расширенных символов (два байта). Если источника и назначения перекрываются, то поведение **memcpy_s** не определено. Используйте **memmove_s** для обработки перекрывающихся областей.

Эти функции проверяют свои параметры. Если *число* не равно нулю и *dest* или *src* является пустым указателем, или *destSize* меньше, чем *число*, эти функции вызывают обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции возвращают **EINVAL** или **ERANGE** и задайте **errno** к возвращаемому значению.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**memcpy_s**|\<memory.h> или \<string.h>|
|**wmemcpy_s**|\<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_memcpy_s.c
// Copy memory in a more secure way.

#include <memory.h>
#include <stdio.h>

int main()
{
   int a1[10], a2[100], i;
   errno_t err;

   // Populate a2 with squares of integers
   for (i = 0; i < 100; i++)
   {
      a2[i] = i*i;
   }

   // Tell memcpy_s to copy 10 ints (40 bytes), giving
   // the size of the a1 array (also 40 bytes).
   err = memcpy_s(a1, sizeof(a1), a2, 10 * sizeof (int) );
   if (err)
   {
      printf("Error executing memcpy_s.\n");
   }
   else
   {
     for (i = 0; i < 10; i++)
       printf("%d ", a1[i]);
   }
   printf("\n");
}
```

```Output
0 1 4 9 16 25 36 49 64 81
```

## <a name="see-also"></a>См. также

[Манипуляция буфером](../../c-runtime-library/buffer-manipulation.md)<br/>
[_memccpy](memccpy.md)<br/>
[memchr, wmemchr](memchr-wmemchr.md)<br/>
[memcmp, wmemcmp](memcmp-wmemcmp.md)<br/>
[memmove, wmemmove](memmove-wmemmove.md)<br/>
[memset, wmemset](memset-wmemset.md)<br/>
[strcpy, wcscpy, _mbscpy](strcpy-wcscpy-mbscpy.md)<br/>
[strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)<br/>
[strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)<br/>
