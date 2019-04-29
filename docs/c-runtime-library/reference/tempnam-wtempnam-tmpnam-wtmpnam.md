---
title: _tempnam, _wtempnam, tmpnam, _wtmpnam
ms.date: 11/04/2016
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
ms.openlocfilehash: 29fa8fc836b1b52bcf66247b3f6aaba47b8c2eaa
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62284876"
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

*префикс*<br/>
Строка, будет добавляться к именам, возвращенный **_tempnam**.

*dir*<br/>
Путь, используемый в имени файла, если переменная среды TMP отсутствует или TMP не является допустимым каталогом.

*str*<br/>
Указатель, который будет содержать формируемое имя и совпадать с именем, возвращенным функцией. Это удобный способ сохранения формируемого имени.

## <a name="return-value"></a>Возвращаемое значение

Каждая из этих функций возвращает указатель на имя создаваемого или **NULL** в случае сбоя. Сбой может возникать при попытке более **TMP_MAX** (см. в разделе STDIO. H) вызовов с **tmpnam** или если вы используете **_tempnam** и указано недопустимое имя каталога в переменной среды TMP и в *dir* параметра.

> [!NOTE]
> Указатели, возвращенные функциями **tmpnam** и **_wtmpnam** указывать на внутренние статические буфера. Для освобождения этих указателей не следует вызывать функцию [free](free.md). **бесплатный** должен вызываться для указателей, выделенных функциями **_tempnam** и **_wtempnam**.

## <a name="remarks"></a>Примечания

Каждая из этих функций возвращает имя файла, который в данный момент не существует. **tmpnam** возвращает имя, которое является уникальным в заданный Windows каталог временного возвращаемые [GetTempPathW](/windows/desktop/api/fileapi/nf-fileapi-gettemppathw). **\_tempnam** создает уникальное имя в каталог, отличный от указанного. Заметьте, что если в начало имени файла добавляется обратная косая черта без сведений о пути, например \fname21, это означает, что имя является допустимым для текущей рабочей папки.

Для **tmpnam**, вы можете хранить это имя созданного файла в *str*. Если *str* — **NULL**, затем **tmpnam** оставляет результат во внутреннем статическом буфере. Поэтому все последующие вызовы уничтожают это значение. Имя, созданное функцией **tmpnam** состоит из имени файла и после первого вызова **tmpnam**, расширение файла из последовательных чисел с основанием 32 (.1 – .vvu, если **TMP_MAX**  в STDIO. H — 32 767).

**_tempnam** будет создавать уникальное имя файла для каталога, выбранного по следующим правилам:

- Если переменная среды TMP определена и в ней задано допустимое имя каталога, уникальные имена файлов формируются для указанного каталога TMP.

- Если переменная среды TMP не определена или если ему будет присвоено имя каталога, который не существует, **_tempnam** будет использовать *dir* параметра в виде пути, для которого она будет формировать уникальные имена.

- Если переменная среды TMP не определена или если ему будет присвоено имя каталога, который не существует и *dir* либо **NULL** или задать имя каталога, который не существует, **_ tempnam** будет использовать текущий рабочий каталог для формирования уникальных имен. В настоящее время Если и TMP и *dir* укажите имена каталогов, которые не существуют, **_tempnam** вызов функции завершится ошибкой.

Имя, возвращенное **_tempnam** будет объединение *префикс* и порядкового номера, образующих уникальное имя файла для указанного каталога. **_tempnam** создает имена файлов, не имеющие расширение. **_tempnam** использует [malloc](malloc.md) выделить место для имени файла; программа отвечает за освобождение этого пространства, когда он больше не нужен.

**_tempnam** и **tmpnam** автоматически дескриптор многобайтовые строковые аргументы должным образом, распознавая последовательности многобайтовых символов согласно кодовой странице OEM, полученная от операционной системы. **_wtempnam** — это двухбайтовая версия **_tempnam**; аргументы и возвращаемое значение **_wtempnam** представляют собой строки расширенных символов. **_wtempnam** и **_tempnam** ведут себя одинаково, за исключением случаев, **_wtempnam** не обрабатывает многобайтовые строки. **_wtmpnam** — это двухбайтовая версия **tmpnam**; аргумент и возвращаемое значение **_wtmpnam** представляют собой строки расширенных символов. **_wtmpnam** и **tmpnam** ведут себя одинаково, за исключением случаев, **_wtmpnam** не обрабатывает многобайтовые строки.

Если **_DEBUG** и **_CRTDBG_MAP_ALLOC** определены, **_tempnam** и **_wtempnam** заменяются вызовами функций для [_tempnam _dbg и _wtempnam_dbg](tempnam-dbg-wtempnam-dbg.md).

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

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
// temporary directory, and _tempname to create a unique filename
// in C:\\tmp.

#include <stdio.h>
#include <stdlib.h>

int main(void)
{
   char * name1 = NULL;
   char * name2 = NULL;
   char * name3 = NULL;

   // Create a temporary filename for the current working directory:
   if ((name1 = tmpnam(NULL)) != NULL) { // C4996
   // Note: tmpnam is deprecated; consider using tmpnam_s instead
      printf("%s is safe to use as a temporary file.\n", name1);
   } else {
      printf("Cannot create a unique filename\n");
   }

   // Create a temporary filename in temporary directory with the
   // prefix "stq". The actual destination directory may vary
   // depending on the state of the TMP environment variable and
   // the global variable P_tmpdir.

   if ((name2 = _tempnam("c:\\tmp", "stq")) != NULL) {
      printf("%s is safe to use as a temporary file.\n", name2);
   } else {
      printf("Cannot create a unique filename\n");
   }

   // When name2 is no longer needed:
   if (name2) {
      free(name2);
   }

   // Unset TMP environment variable, then create a temporary filename in C:\tmp.
   if (_putenv("TMP=") != 0) {
      printf("Could not remove TMP environment variable.\n");
   }

   // With TMP unset, we will use C:\tmp as the temporary directory.
   // Create a temporary filename in C:\tmp with prefix "stq".
   if ((name3 = _tempnam("c:\\tmp", "stq")) != NULL) {
      printf("%s is safe to use as a temporary file.\n", name3);
   }
   else {
      printf("Cannot create a unique filename\n");
   }

   // When name3 is no longer needed:
   if (name3) {
      free(name3);
   }

   return 0;
}
```

```Output
C:\Users\LocalUser\AppData\Local\Temp\sriw.0 is safe to use as a temporary file.
C:\Users\LocalUser\AppData\Local\Temp\stq2 is safe to use as a temporary file.
c:\tmp\stq3 is safe to use as a temporary file.
```

## <a name="see-also"></a>См. также

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[malloc](malloc.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[tmpfile](tmpfile.md)<br/>
[tmpfile_s](tmpfile-s.md)<br/>
