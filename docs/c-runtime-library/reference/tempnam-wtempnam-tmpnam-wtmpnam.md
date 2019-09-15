---
title: _tempnam, _wtempnam, tmpnam, _wtmpnam
ms.date: 11/04/2016
api_name:
- _wtempnam
- _wtmpnam
- tmpnam
- _tempnam
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
ms.openlocfilehash: 9fd1eb9f2f718afec5b7d5555145fcd7e5cc17cf
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957519"
---
# <a name="_tempnam-_wtempnam-tmpnam-_wtmpnam"></a>_tempnam, _wtempnam, tmpnam, _wtmpnam

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

*prefix*<br/>
Строка, которая будет предваряться именами, возвращаемыми функцией **_tempnam**.

*команды*<br/>
Путь, используемый в имени файла, если переменная среды TMP отсутствует или TMP не является допустимым каталогом.

*str*<br/>
Указатель, который будет содержать формируемое имя и совпадать с именем, возвращенным функцией. Это удобный способ сохранения формируемого имени.

## <a name="return-value"></a>Возвращаемое значение

Каждая из этих функций возвращает указатель на созданное имя или **значение NULL** в случае сбоя. Сбой может произойти при попытке более **TMP_MAX** (см. stdio). H) вызывает метод с **tmpnam** или, если используется **_tempnam** , а в переменной среды TMP и в параметре *dir* указано недопустимое имя каталога.

> [!NOTE]
> Указатели, возвращаемые **tmpnam** и **_wtmpnam** , указывают на внутренние статические буферы. Для освобождения этих указателей не следует вызывать функцию [free](free.md). для указателей, выделенных **_tempnam** и **_wtempnam**, необходимо вызывать **Free** .

## <a name="remarks"></a>Примечания

Каждая из этих функций возвращает имя файла, который в данный момент не существует. **tmpnam** возвращает уникальное имя в указанном временном каталоге Windows, возвращенном [жеттемппасв](/windows/win32/api/fileapi/nf-fileapi-gettemppathw). tempnam создает уникальное имя в каталоге, отличном от назначенного.  **\_** Заметьте, что если в начало имени файла добавляется обратная косая черта без сведений о пути, например \fname21, это означает, что имя является допустимым для текущей рабочей папки.

Для **tmpnam**можно сохранить созданное имя файла в *str*. Если *str* имеет **значение NULL**, **tmpnam** оставляет результат во внутреннем статическом буфере. Поэтому все последующие вызовы уничтожают это значение. Имя, созданное **tmpnam** , состоит из генерируемого программой имени файла и, после первого вызова **tmpnam**, расширения файла последовательных чисел в Base 32 (. 1 –. vvu, когда **TMP_MAX** в stdio. H — 32 767).

**_tempnam** создаст уникальное имя файла для каталога, выбранного следующими правилами.

- Если переменная среды TMP определена и в ней задано допустимое имя каталога, уникальные имена файлов формируются для указанного каталога TMP.

- Если переменная среды TMP не определена или для нее задано имя несуществующего каталога, **_tempnam** будет использовать параметр *dir* в качестве пути, для которого он будет формировать уникальные имена.

- Если переменная среды TMP не определена или для нее задано имя несуществующего каталога, а если параметр *dir* имеет **значение NULL** или имя каталога, который не существует, **_tempnam** будет использовать текущий рабочий каталог для ген Оцените уникальные имена. В настоящее время, если и TMP, и *dir* указывают имена несуществующих каталогов, вызов функции **_tempnam** завершится ошибкой.

Имя, возвращаемое функцией **_tempnam** , будет объединением *префикса* и порядкового номера, который будет сочетаться для создания уникального имени файла для указанного каталога. **_tempnam** создает имена файлов, которые не имеют расширения. **_tempnam** использует [malloc](malloc.md) для выделения пространства имени файла; Программа отвечает за освобождение этого пространства, когда оно больше не требуется.

**_tempnam** и **tmpnam** автоматически обрабатывали строковые аргументы многобайтовых символов соответствующим образом, распознающие последовательности многобайтовых символов в соответствии с кодовой страницей OEM, полученной от операционной системы. **_wtempnam** — это версия **_tempnam**для расширенных символов; аргументы и возвращаемое значение **_wtempnam** являются строками расширенных символов. поведение **_wtempnam** и **_tempnam** идентично, за исключением того, что **_wtempnam** не обрабатывает строки многобайтовых символов. **_wtmpnam** — это версия **tmpnam**для расширенных символов; аргумент и возвращаемое значение **_wtmpnam** являются строками расширенных символов. поведение **_wtmpnam** и **tmpnam** идентично, за исключением того, что **_wtmpnam** не обрабатывает строки многобайтовых символов.

Если определены **_DEBUG** и **_CRTDBG_MAP_ALLOC** , то **_tempnam** и **_wtempnam** заменяются вызовами [_tempnam_dbg и _wtempnam_dbg](tempnam-dbg-wtempnam-dbg.md).

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
