---
title: memcpy_s, wmemcpy_s
ms.date: 4/2/2020
api_name:
- memcpy_s
- wmemcpy_s
- _o_memcpy_s
- _o_wmemcpy_s
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
- api-ms-win-crt-string-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- wmemcpy_s
- memcpy_s
helpviewer_keywords:
- memcpy_s function
- wmemcpy_s function
ms.assetid: 5504e20a-83d9-4063-91fc-3f55f7dabe99
ms.openlocfilehash: dc5e49115b65b6883e55df13d0610231a87c1c55
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81333340"
---
# <a name="memcpy_s-wmemcpy_s"></a>memcpy_s, wmemcpy_s

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

### <a name="error-conditions"></a>Ситуации, которые могут привести к ошибке

|*dest*|*destSize*|*src*|*count*|Возвращаемое значение|Содержание *dest*|
|------------|----------------|-----------|---|------------------|------------------------|
|any|any|any|0|0|Без изменений|
|**Null**|any|any|ненулевое значение|**EINVAL**|Без изменений|
|any|any|**Null**|ненулевое значение|**EINVAL**|*dest* обнуляется|
|any|< *Рассчитывать*|any|ненулевое значение|**ERANGE**|*dest* обнуляется|

## <a name="remarks"></a>Remarks

**memcpy_s** копии *считать* байты от *src* до *dest;* **wmemcpy_s** копии *подсчитывают* широкие символы (два байта). Если источник и пункт назначения перекрываются, поведение **memcpy_s** не определено. Используйте **memmove_s** для обработки перекрывающихся областей.

Эти функции проверяют свои параметры. Если *количество* не равноzero и *dest* или *src* является нулевой указатель, или *destSize* меньше, чем *кол,* эти функции вызывают недействительный обработчик параметров, как описано в [параметре валидации](../../c-runtime-library/parameter-validation.md). Если выполнение разрешено продолжать, эти функции возвращают **EINVAL** или **ERANGE** и устанавливают **errno** к значению возврата.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**memcpy_s**|\<memory.h> или \<string.h>|
|**wmemcpy_s**|\<wchar.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также раздел

[Манипуляция буфером](../../c-runtime-library/buffer-manipulation.md)<br/>
[_memccpy](memccpy.md)<br/>
[memchr, wmemchr](memchr-wmemchr.md)<br/>
[memcmp, wmemcmp](memcmp-wmemcmp.md)<br/>
[memmove, wmemmove](memmove-wmemmove.md)<br/>
[memset, wmemset](memset-wmemset.md)<br/>
[strcpy, wcscpy, _mbscpy](strcpy-wcscpy-mbscpy.md)<br/>
[strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)<br/>
[strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)<br/>
