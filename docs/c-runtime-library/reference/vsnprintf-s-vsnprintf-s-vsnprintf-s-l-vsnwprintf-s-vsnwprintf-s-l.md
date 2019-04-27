---
title: vsnprintf_s, _vsnprintf_s, _vsnprintf_s_l, _vsnwprintf_s, _vsnwprintf_s_l
ms.date: 11/04/2016
apiname:
- _vsnwprintf_s
- _vsnwprintf_s_l
- _vsnprintf_s
- vsnprintf_s
- _vsnprintf_s_l
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
- ntdll.dll
- ucrtbase.dll
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- _vsnprintf_s
- _vsntprintf_s
- _vsnwprintf_s
helpviewer_keywords:
- vsnwprintf_s function
- _vsntprintf_s function
- _vsntprintf_s_l function
- vsntprintf_s function
- vsnwprintf_s_l function
- vsnprintf_s_l function
- vsntprintf_s_l function
- _vsnwprintf_s_l function
- _vsnprintf_s function
- vsnprintf_s function
- _vsnprintf_s_l function
- _vsnwprintf_s function
- formatted text [C++]
ms.assetid: 147ccfce-58c7-4681-a726-ef54ac1c604e
ms.openlocfilehash: 255c3b760dec1495a4f9a82915878a5504844f24
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62188730"
---
# <a name="vsnprintfs-vsnprintfs-vsnprintfsl-vsnwprintfs-vsnwprintfsl"></a>vsnprintf_s, _vsnprintf_s, _vsnprintf_s_l, _vsnwprintf_s, _vsnwprintf_s_l

Записывают форматированные выходные данные с помощью указателя на список аргументов. Это версии функций [vsnprintf, _vsnprintf, _vsnprintf_l, _vsnwprintf, _vsnwprintf_l](vsnprintf-vsnprintf-vsnprintf-l-vsnwprintf-vsnwprintf-l.md) с усовершенствованной безопасностью, как описано в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Синтаксис

```C
int vsnprintf_s(
   char *buffer,
   size_t sizeOfBuffer,
   size_t count,
   const char *format,
   va_list argptr
);
int _vsnprintf_s(
   char *buffer,
   size_t sizeOfBuffer,
   size_t count,
   const char *format,
   va_list argptr
);
int _vsnprintf_s_l(
   char *buffer,
   size_t sizeOfBuffer,
   size_t count,
   const char *format,
   locale_t locale,
   va_list argptr
);
int _vsnwprintf_s(
   wchar_t *buffer,
   size_t sizeOfBuffer,
   size_t count,
   const wchar_t *format,
   va_list argptr
);
int _vsnwprintf_s_l(
   wchar_t *buffer,
   size_t sizeOfBuffer,
   size_t count,
   const wchar_t *format,
   locale_t locale,
   va_list argptr
);
template <size_t size>
int _vsnprintf_s(
   char (&buffer)[size],
   size_t count,
   const char *format,
   va_list argptr
); // C++ only
template <size_t size>
int _vsnwprintf_s(
   wchar_t (&buffer)[size],
   size_t count,
   const wchar_t *format,
   va_list argptr
); // C++ only
```

### <a name="parameters"></a>Параметры

*buffer*<br/>
Место хранения выходных данных.

*sizeOfBuffer*<br/>
Размер *буфера* для вывода, как количество символов.

*count*<br/>
Максимальное количество символов для записи (не включая завершающий нуль-символ) или [_TRUNCATE](../../c-runtime-library/truncate.md).

*format*<br/>
Спецификация формата.

*argptr*<br/>
Указатель на список аргументов.

*locale*<br/>
Используемый языковой стандарт.

Дополнительные сведения см. в разделе [Спецификации формата](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

## <a name="return-value"></a>Возвращаемое значение

**vsnprintf_s**, **_vsnprintf_s** и **_vsnwprintf_s** возвращают число записанных символов, не включая завершающий символ null, или отрицательное значение, если произошла ошибка вывода. **vsnprintf_s** идентична **_vsnprintf_s**. **vsnprintf_s** включен для соответствия стандарту ANSI. **_vnsprintf** сохраняется для обеспечения обратной совместимости.

Если объем памяти, необходимый для хранения данных и конечного нуль-символа, превышает *sizeOfBuffer*, вызывается обработчик недопустимого параметра, как описано в разделе [проверка параметров](../../c-runtime-library/parameter-validation.md), если не *count*  — [_TRUNCATE](../../c-runtime-library/truncate.md), тогда как строки будет заполнен *буфера* записывается и возвращается значение – 1. Если выполнение продолжается после обработчика недопустимых параметров, эти функции устанавливают *буфера* пустую строку, задайте **errno** для **ERANGE**и возвращают -1.

Если *буфера* или *формат* — **NULL** указателем, или если *число* меньше или равен нулю, вызывается обработчик недопустимого параметра. Если выполнение может быть продолжено, эти функции устанавливают **errno** для **EINVAL** и возвращают -1.

### <a name="error-conditions"></a>Условия ошибок

|**условие**|Назад|**errno**|
|-----------------|------------|-------------|
|*буфер* является **NULL**|-1|**EINVAL**|
|*формат* является **NULL**|-1|**EINVAL**|
|*число* < = 0|-1|**EINVAL**|
|*sizeOfBuffer* слишком мал (и *число* ! = **_TRUNCATE**)|значение -1 (и *буфера* присваивается пустая строка)|**ERANGE**|

## <a name="remarks"></a>Примечания

Каждая из этих функций принимает указатель на список аргументов, а затем форматирует и записывает до *число* символов заданных данных в памяти, на который указывает *буфера* и добавляет завершающий нуль-символ.

Если *число* — [_TRUNCATE](../../c-runtime-library/truncate.md), эти функции выполняют запись строки будет заполнен *буфера* оставить место для конечного нуль-символа. Если вся строка (с учетом завершающего нуль) помещается *буфера*, затем эти функции возвращают количество записанных символов (не включая завершающий нуль-символ); в противном случае эти функции возвращают значение -1, чтобы указать, что усечение Произошла.

Версии этих функций с **_l** суффиксом идентичны, за исключением того, что они используют переданный параметр языкового стандарта вместо языкового стандарта текущего потока.

> [!IMPORTANT]
> Убедитесь, что *format* не является строкой, определяемой пользователем. Дополнительные сведения см. в разделе [Как избежать переполнения буфера](/windows/desktop/SecBP/avoiding-buffer-overruns).

> [!NOTE]
> Чтобы убедиться, что достаточно места для завершающего нуль-символа, убедитесь, что *число* строго меньше размера буфера, или используйте **_TRUNCATE**.

В C++ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера (что исключает необходимость указания аргумента с размером буфера), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами. Дополнительные сведения см. в разделе [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vsntprintf_s**|**_vsnprintf_s**|**_vsnprintf_s**|**_vsnwprintf_s**|
|**_vsntprintf_s_l**|**_vsnprintf_s_l**|**_vsnprintf_s_l**|**_vsnwprintf_s_l**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательные заголовки|
|-------------|---------------------|----------------------|
|**vsnprintf_s**|\<stdio.h> и \<stdarg.h>|\<varargs.h>*|
|**_vsnprintf_s**, **_vsnprintf_s_l**|\<stdio.h> и \<stdarg.h>|\<varargs.h>*|
|**_vsnwprintf_s**, **_vsnwprintf_s_l**|\<stdio.h> или \<wchar.h> и \<stdarg.h>|\<varargs.h>*|

\* Требуется для совместимости с UNIX V.

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```cpp
// crt_vsnprintf_s.cpp
#include <stdio.h>
#include <wtypes.h>

void FormatOutput(LPCSTR formatstring, ...)
{
   int nSize = 0;
   char buff[10];
   memset(buff, 0, sizeof(buff));
   va_list args;
   va_start(args, formatstring);
   nSize = vsnprintf_s( buff, _countof(buff), _TRUNCATE, formatstring, args);
   printf("nSize: %d, buff: %s\n", nSize, buff);
   va_end(args);
}

int main() {
   FormatOutput("%s %s", "Hi", "there");
   FormatOutput("%s %s", "Hi", "there!");
   FormatOutput("%s %s", "Hi", "there!!");
}
```

```Output
nSize: 8, buff: Hi there
nSize: 9, buff: Hi there!
nSize: -1, buff: Hi there!
```

## <a name="see-also"></a>См. также

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[Функции vprintf](../../c-runtime-library/vprintf-functions.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[va_arg, va_copy, va_end, va_start](va-arg-va-copy-va-end-va-start.md)<br/>
