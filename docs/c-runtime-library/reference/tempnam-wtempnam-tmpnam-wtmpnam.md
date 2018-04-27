---
title: _tempnam, _wtempnam, tmpnam, _wtmpnam | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _wtempnam
- _wtmpnam
- tmpnam
- _tempnam
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
- wtempnam
- _wtmpnam
- wtmpnam
- tmpnam
- _wtempnam
- _tempnam
dev_langs:
- C++
helpviewer_keywords:
- wtempnam function
- file names [C++], creating temporary
- _tempnam function
- ttmpnam function
- tmpnam function
- tempnam function
- wtmpnam function
- temporary files, creating
- file names [C++], temporary
- _ttmpnam function
- _wtmpnam function
- _wtempnam function
ms.assetid: 3ce75f0f-5e30-42a6-9791-8d7cbfe70fca
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4ba00c1998a41f2d17408babc87b0bf45cad689b
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
# <a name="tempnam-wtempnam-tmpnam-wtmpnam"></a>_tempnam, _wtempnam, tmpnam, _wtmpnam

Формирует имена, которые можно использовать для создания временных файлов. Существуют более безопасные версии этих функций; см. статью [tmpnam_s, _wtmpnam_s](tmpnam-s-wtmpnam-s.md).

## <a name="syntax"></a>Синтаксис

```C
char *_tempnam(
   const char *dir,
   const char *prefix
);
wchar_t *_wtempnam(
   const wchar_t *dir,
   const wchar_t *prefix
);
char *tmpnam(
   char *str
);
wchar_t *_wtmpnam(
   wchar_t *str
);
```

### <a name="parameters"></a>Параметры

*Префикс*<br/>
Строка, которая добавляется в начало имен, возвращаемых **_tempnam**.

*dir*<br/>
Путь, используемый в имени файла, если переменная среды TMP отсутствует или TMP не является допустимым каталогом.

*str*<br/>
Указатель, который будет содержать формируемое имя и совпадать с именем, возвращенным функцией. Это удобный способ сохранения формируемого имени.

## <a name="return-value"></a>Возвращаемое значение

Каждая из этих функций возвращает указатель на формируемое имя или **NULL** при неудачном завершении. Сбой может возникать при попытке более **TMP_MAX** (STDIO см. H) вызовов с **tmpnam** или если вы используете **_tempnam** и указано недопустимое имя каталога в переменной среды TMP и *dir* параметра.

> [!NOTE]
> Указатели, возвращенные **tmpnam** и **_wtmpnam** пункты внутренние статические буфера. Для освобождения этих указателей не следует вызывать функцию [free](free.md). **Бесплатные** нужно вызывать для указателей, выделенных функциями **_tempnam** и **_wtempnam**.

## <a name="remarks"></a>Примечания

Каждая из этих функций возвращает имя файла, который в данный момент не существует. **tmpnam** возвращает имя, уникальное в текущем рабочем каталоге и **_tempnam** позволяет сформировать уникальное имя в папке, отличной от текущей. Заметьте, что если в начало имени файла добавляется обратная косая черта без сведений о пути, например \fname21, это означает, что имя является допустимым для текущей рабочей папки.

Для **tmpnam**, можно сохранить это сформированное имя файла в *str*. Если *str* — **NULL**, затем **tmpnam** оставляет результат во внутреннем статическом буфере. Поэтому все последующие вызовы уничтожают это значение. Имя, созданное **tmpnam** состоит из имени файла, созданный программой и после первого вызова **tmpnam**, расширение файла из последовательных чисел с основанием 32 (.1 – .vvu, если **TMP_MAX**  в STDIO. H — 32 767).

**_tempnam** создает уникальное имя файла для каталога, выбранного по следующим правилам:

- Если переменная среды TMP определена и в ней задано допустимое имя каталога, уникальные имена файлов формируются для указанного каталога TMP.

- Если переменная среды TMP не определена или если ему присваивается имя каталога, который не существует, **_tempnam** будет использовать *dir* параметра в виде пути, для которого формируются уникальные имена.

- Если переменная среды TMP не определена или если ему присваивается имя каталога, который не существует и *dir* либо **NULL** или задайте имя каталога, который не существует, **_ tempnam** будет использовать текущий рабочий каталог для формирования уникальных имен. В настоящее время Если и TMP и *dir* укажите имена каталогов, которые не существуют, **_tempnam** функция вызов завершится ошибкой.

Имя, возвращенное **_tempnam** будет объединением из *префикс* и порядкового номера, образующих уникальное имя файла для указанного каталога. **_tempnam** формирует имена файлов, не имеющие расширение. **_tempnam** использует [malloc](malloc.md) для выделения пространства для файла; программа отвечает за освобождение этого пространства, когда он больше не нужен.

**_tempnam** и **tmpnam** автоматически корректно обрабатывают многобайтовые строковые аргументы, распознавая последовательности многобайтовых символов согласно кодовой странице OEM, полученной от операционной системы. **_wtempnam** — это двухбайтовая версия **_tempnam**; аргументы и возвращаемое значение **_wtempnam** представляют собой строки расширенных символов. **_wtempnam** и **_tempnam** ведут себя одинаково, за исключением того, что **_wtempnam** не обрабатывает многобайтовые строки. **_wtmpnam** — это двухбайтовая версия **tmpnam**; аргумент и возвращаемое значение **_wtmpnam** представляют собой строки расширенных символов. **_wtmpnam** и **tmpnam** ведут себя одинаково, за исключением того, что **_wtmpnam** не обрабатывает многобайтовые строки.

Если **_DEBUG** и **_CRTDBG_MAP_ALLOC** определены, **_tempnam** и **_wtempnam** заменяются вызовами функций для [_tempnam _dbg и _wtempnam_dbg](tempnam-dbg-wtempnam-dbg.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ttmpnam**|**tmpnam**|**tmpnam**|**_wtmpnam**|
|**_ttempnam**|**_tempnam**|**_tempnam**|**_wtempnam**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_tempnam**|\<stdio.h>|
|**_wtempnam**, **_wtmpnam**|\<stdio.h> или \<wchar.h>|
|**tmpnam**|\<stdio.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_tempnam.c
// compile with: /W3
// This program uses tmpnam to create a unique filename in the
// current working directory, then uses _tempnam to create
// a unique filename with a prefix of stq.

#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   char* name1 = NULL;
   char* name2 = NULL;

   // Create a temporary filename for the current working directory:
   if( ( name1 = tmpnam( NULL ) ) != NULL ) // C4996
   // Note: tmpnam is deprecated; consider using tmpnam_s instead
      printf( "%s is safe to use as a temporary file.\n", name1 );
   else
      printf( "Cannot create a unique filename\n" );

   // Create a temporary filename in temporary directory with the
   // prefix "stq". The actual destination directory may vary
   // depending on the state of the TMP environment variable and
   // the global variable P_tmpdir.

   if( ( name2 = _tempnam( "c:\\tmp", "stq" ) ) != NULL )
      printf( "%s is safe to use as a temporary file.\n", name2 );
   else
      printf( "Cannot create a unique filename\n" );

   // When name2 is no longer needed :
   if(name2)
     free(name2);

}
```

```Output
\s1gk. is safe to use as a temporary file.
C:\DOCUME~1\user\LOCALS~1\Temp\2\stq2 is safe to use as a temporary file.
```

## <a name="see-also"></a>См. также

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[malloc](malloc.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[tmpfile](tmpfile.md)<br/>
[tmpfile_s](tmpfile-s.md)<br/>
