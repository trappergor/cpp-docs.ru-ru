---
title: tmpnam_s _wtmpnam_s | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- tmpnam_s
- _wtmpnam_s
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- tmpnam_s
- _wtmpnam_s
- L_tmpnam_s
dev_langs:
- C++
helpviewer_keywords:
- tmpnam_s function
- file names [C++], creating temporary
- _wtmpnam_s function
- L_tmpnam_s constant
- temporary files, creating
- file names [C++], temporary
- wtmpnam_s function
ms.assetid: e70d76dc-49f5-4aee-bfa2-f1baa2bcd29f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d8c6298c7b66c8967a4e5e23a37c3614edcddf3d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32415533"
---
# <a name="tmpnams-wtmpnams"></a>tmpnam_s, _wtmpnam_s

Формирует имена, которые можно использовать для создания временных файлов. Это версии функций [tmpnam и _wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md) с усовершенствованной безопасностью, как описано в разделе [Усовершенствования безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Синтаксис

```C
errno_t tmpnam_s(
   char * str,
   size_t sizeInChars
);
errno_t _wtmpnam_s(
   wchar_t *str,
   size_t sizeInChars
);
template <size_t size>
errno_t tmpnam_s(
   char (&str)[size]
); // C++ only
template <size_t size>
errno_t _wtmpnam_s(
   wchar_t (&str)[size]
); // C++ only
```

### <a name="parameters"></a>Параметры

*str*<br/>
Указатель, который будет содержать сформированное имя.

*sizeInChars*<br/>
Размер буфера в символах.

## <a name="return-value"></a>Возвращаемое значение

Обе эти функции возвращают 0 в случае успеха или номер ошибки в случае сбоя.

### <a name="error-conditions"></a>Условия ошибок

|||||
|-|-|-|-|
|*str*|*sizeInChars*|**Возвращаемое значение**|**Содержимое***str* |
|**NULL**|any|**EINVAL**|не изменено|
|Не **NULL** (указывает на допустимый адрес в памяти)|слишком короткий|**ERANGE**|не изменено|

Если *str* — **NULL**, вызывается обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции устанавливают **errno** для **EINVAL** и возвращают **EINVAL**.

## <a name="remarks"></a>Примечания

Каждая из этих функций возвращает имя файла, который в данный момент не существует. **tmpnam_s** возвращает имя, уникальное в текущем рабочем каталоге. Заметьте, что если в начало имени файла добавляется обратная косая черта без сведений о пути, например \fname21, это означает, что имя является допустимым для текущей рабочей папки.

Для **tmpnam_s**, можно сохранить это сформированное имя файла в *str*. Максимальная длина строки, возвращенные **tmpnam_s** — **L_tmpnam_s**, определенный в STDIO. З. Если *str* — **NULL**, затем **tmpnam_s** оставляет результат во внутреннем статическом буфере. Поэтому все последующие вызовы уничтожают это значение. Имя, созданное **tmpnam_s** состоит из имени файла, созданный программой и после первого вызова **tmpnam_s**, расширение файла из последовательных чисел с основанием 32 (.1-.1vvvvvu, если **TMP _MAX_S** в STDIO. H- **INT_MAX**).

**tmpnam_s** автоматически обрабатывает многобайтовые строковые аргументы соответствующим образом, распознавая последовательности многобайтовых символов согласно кодовой странице OEM, полученной от операционной системы. **_wtmpnam_s** — это двухбайтовая версия **tmpnam_s**; аргумент и возвращаемое значение **_wtmpnam_s** представляют собой строки расширенных символов. **_wtmpnam_s** и **tmpnam_s** ведут себя одинаково, за исключением того, что **_wtmpnam_s** не обрабатывает многобайтовые строки.

В C++ использование этих функций упрощено шаблонными перегрузками; перегрузки могут определить длину буфера автоматически, устраняя необходимость указывать аргумент size. Дополнительные сведения см. в разделе [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ttmpnam_s**|**tmpnam_s**|**tmpnam_s**|**_wtmpnam_s**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**tmpnam_s**|\<stdio.h>|
|**_wtmpnam_s**|\<stdio.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_tmpnam_s.c
// This program uses tmpnam_s to create a unique filename in the
// current working directory.
//

#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   char name1[L_tmpnam_s];
   errno_t err;
   int i;

   for (i = 0; i < 15; i++)
   {
      err = tmpnam_s( name1, L_tmpnam_s );
      if (err)
      {
         printf("Error occurred creating unique filename.\n");
         exit(1);
      }
      else
      {
         printf( "%s is safe to use as a temporary file.\n", name1 );
      }
   }
}
```

## <a name="see-also"></a>См. также

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[malloc](malloc.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[tmpfile_s](tmpfile-s.md)<br/>
