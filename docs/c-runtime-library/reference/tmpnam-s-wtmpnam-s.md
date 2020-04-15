---
title: tmpnam_s, _wtmpnam_s
ms.date: 4/2/2020
api_name:
- tmpnam_s
- _wtmpnam_s
- _o__wtmpnam_s
- _o_tmpnam_s
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: e34fbe64d342205659a4b0bdaf703248e62ed733
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81362416"
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

*Ул*<br/>
Указатель, который будет содержать сформированное имя.

*размерInChars*<br/>
Размер буфера в символах.

## <a name="return-value"></a>Возвращаемое значение

Обе эти функции возвращают 0 в случае успеха или номер ошибки в случае сбоя.

### <a name="error-conditions"></a>Ситуации, которые могут привести к ошибке

|||||
|-|-|-|-|
|*Ул*|*размерInChars*|**Значение возврата**|**Содержимое**  *str*|
|**Null**|any|**EINVAL**|не изменено|
|не **NULL** (указывает на действительную память)|слишком короткий|**ERANGE**|не изменено|

Если *str* str **null,** вызовуется недействительный обработчик параметров, как описано в [проверке параметра.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, эти функции установить **errno** **eINVAL** и вернуть **EINVAL**.

## <a name="remarks"></a>Remarks

Каждая из этих функций возвращает имя файла, который в данный момент не существует. **tmpnam_s** возвращает имя, уникальное в специально отведенном временном каталоге Windows, возвращенном [GetTempPathW.](/windows/win32/api/fileapi/nf-fileapi-gettemppathw) Заметьте, что если в начало имени файла добавляется обратная косая черта без сведений о пути, например \fname21, это означает, что имя является допустимым для текущей рабочей папки.

Для **tmpnam_s**вы можете хранить это генерируемое имя файла в *str*. Максимальная длина строки, возвращенной **tmpnam_s,** **L_tmpnam_s,** определенная в STDIO. H. Если *str* str **null,** то **tmpnam_s** оставляет результат во внутреннем статическом буфере. Поэтому все последующие вызовы уничтожают это значение. Имя, генерируемое **tmpnam_s,** состоит из генерируемого программой имени файла и, после первого звонка **в tmpnam_s,** расширения файла последовательных чисел в базе 32 (.1-.1vvvvvu, когда **TMP_MAX_S** в STDIO. H **INT_MAX).**

**tmpnam_s** автоматически обрабатывает аргументы строки мультибайт-символа по мере необходимости, распознавая последовательности мультибайт-символов в соответствии со страницей кода OEM, полученной из операционной системы. **_wtmpnam_s** является широкохарактерным вариантом **tmpnam_s;** аргументом и значением возврата **_wtmpnam_s** являются широкохарактерные строки. **_wtmpnam_s** и **tmpnam_s** ведут себя одинаково, за исключением того, что **_wtmpnam_s** не обрабатывает строки с мультибайт-символами.

В C++ использование этих функций упрощено шаблонными перегрузками; перегрузки могут определить длину буфера автоматически, устраняя необходимость указывать аргумент size. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ttmpnam_s**|**tmpnam_s**|**tmpnam_s**|**_wtmpnam_s**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**tmpnam_s**|\<stdio.h>|
|**_wtmpnam_s**|\<stdio.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также раздел

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[malloc](malloc.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[tmpfile_s](tmpfile-s.md)<br/>
