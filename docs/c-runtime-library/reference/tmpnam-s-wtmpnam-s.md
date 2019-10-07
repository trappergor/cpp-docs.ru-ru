---
title: tmpnam_s, _wtmpnam_s
ms.date: 11/04/2016
api_name:
- tmpnam_s
- _wtmpnam_s
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- tmpnam_s
- _wtmpnam_s
- L_tmpnam_s
helpviewer_keywords:
- tmpnam_s function
- file names [C++], creating temporary
- _wtmpnam_s function
- L_tmpnam_s constant
- temporary files, creating
- file names [C++], temporary
- wtmpnam_s function
ms.assetid: e70d76dc-49f5-4aee-bfa2-f1baa2bcd29f
ms.openlocfilehash: 847df0d2369857d009c39b4dd61adce45094899c
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70946044"
---
# <a name="tmpnam_s-_wtmpnam_s"></a>tmpnam_s, _wtmpnam_s

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

*сизеинчарс*<br/>
Размер буфера в символах.

## <a name="return-value"></a>Возвращаемое значение

Обе эти функции возвращают 0 в случае успеха или номер ошибки в случае сбоя.

### <a name="error-conditions"></a>Условия ошибок

|||||
|-|-|-|-|
|*str*|*сизеинчарс*|**Возвращаемое значение**|**Содержимое** *str*|
|**NULL**|Любое действие|**EINVAL**|не изменено|
|Not **null** (указывает на допустимый объем памяти)|слишком короткий|**ERANGE**|не изменено|

Если *str* имеет **значение NULL**, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции **устанавливают** значение **еинвал** и возвращают **еинвал**.

## <a name="remarks"></a>Примечания

Каждая из этих функций возвращает имя файла, который в данный момент не существует. **tmpnam_s** возвращает имя, уникальное в указанном временном каталоге Windows, возвращенном [жеттемппасв](/windows/win32/api/fileapi/nf-fileapi-gettemppathw). Заметьте, что если в начало имени файла добавляется обратная косая черта без сведений о пути, например \fname21, это означает, что имя является допустимым для текущей рабочей папки.

Для **tmpnam_s**можно сохранить созданное имя файла в *str*. Максимальная длина строки, возвращаемой функцией **tmpnam_s** , — **L_tmpnam_s**, определенная в stdio. Высоты. Если *str* имеет **значение NULL**, **tmpnam_s** оставляет результат во внутреннем статическом буфере. Поэтому все последующие вызовы уничтожают это значение. Имя, созданное **tmpnam_s** , состоит из генерируемого программой имени файла и, после первого вызова **tmpnam_s**, расширения файла последовательных чисел в Base 32 (. 1-. 1vvvvvu, когда **TMP_MAX_S** в stdio. H — **INT_MAX**).

**tmpnam_s** автоматически обрабатывает строковые аргументы многобайтовых символов соответствующим образом, распознает последовательности многобайтовых символов в соответствии с кодовой СТРАНИЦЕй OEM, полученной от операционной системы. **_wtmpnam_s** — это версия **tmpnam_s**для расширенных символов; аргумент и возвращаемое значение **_wtmpnam_s** являются строками расширенных символов. поведение **_wtmpnam_s** и **tmpnam_s** идентично, за исключением того, что **_wtmpnam_s** не обрабатывает строки многобайтовых символов.

В C++ использование этих функций упрощено шаблонными перегрузками; перегрузки могут определить длину буфера автоматически, устраняя необходимость указывать аргумент size. Дополнительные сведения см. в разделе [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

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

```Output
C:\Users\LocalUser\AppData\Local\Temp\u19q8.0 is safe to use as a temporary file.
C:\Users\LocalUser\AppData\Local\Temp\u19q8.1 is safe to use as a temporary file.
C:\Users\LocalUser\AppData\Local\Temp\u19q8.2 is safe to use as a temporary file.
C:\Users\LocalUser\AppData\Local\Temp\u19q8.3 is safe to use as a temporary file.
C:\Users\LocalUser\AppData\Local\Temp\u19q8.4 is safe to use as a temporary file.
C:\Users\LocalUser\AppData\Local\Temp\u19q8.5 is safe to use as a temporary file.
C:\Users\LocalUser\AppData\Local\Temp\u19q8.6 is safe to use as a temporary file.
C:\Users\LocalUser\AppData\Local\Temp\u19q8.7 is safe to use as a temporary file.
C:\Users\LocalUser\AppData\Local\Temp\u19q8.8 is safe to use as a temporary file.
C:\Users\LocalUser\AppData\Local\Temp\u19q8.9 is safe to use as a temporary file.
C:\Users\LocalUser\AppData\Local\Temp\u19q8.a is safe to use as a temporary file.
C:\Users\LocalUser\AppData\Local\Temp\u19q8.b is safe to use as a temporary file.
C:\Users\LocalUser\AppData\Local\Temp\u19q8.c is safe to use as a temporary file.
C:\Users\LocalUser\AppData\Local\Temp\u19q8.d is safe to use as a temporary file.
C:\Users\LocalUser\AppData\Local\Temp\u19q8.e is safe to use as a temporary file.
```

## <a name="see-also"></a>См. также

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[malloc](malloc.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[tmpfile_s](tmpfile-s.md)<br/>
