---
title: "vsnprintf_s, _vsnprintf_s, _vsnprintf_s_l, _vsnwprintf_s, _vsnwprintf_s_l | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
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
apitype: DLLExport
f1_keywords:
- _vsnprintf_s
- _vsntprintf_s
- _vsnwprintf_s
dev_langs:
- C++
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6e908750b54778d4aad7affeb6bd748a84ab39bc
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="vsnprintfs-vsnprintfs-vsnprintfsl-vsnwprintfs-vsnwprintfsl"></a>vsnprintf_s, _vsnprintf_s, _vsnprintf_s_l, _vsnwprintf_s, _vsnwprintf_s_l
Записывают форматированные выходные данные с помощью указателя на список аргументов. Это версии функций [vsnprintf, _vsnprintf, _vsnprintf_l, _vsnwprintf, _vsnwprintf_l](../../c-runtime-library/reference/vsnprintf-vsnprintf-vsnprintf-l-vsnwprintf-vsnwprintf-l.md) с усовершенствованной безопасностью, как описано в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
  
#### <a name="parameters"></a>Параметры  
 `buffer`  
 Место хранения выходных данных.  
  
 `sizeOfBuffer`  
 Размер `buffer` для вывода, как количество символов.  
  
 `count`  
 Максимальное количество символов для записи (не включая завершающий нуль-символ) или [_TRUNCATE](../../c-runtime-library/truncate.md).  
  
 `format`  
 Спецификация формата.  
  
 `argptr`  
 Указатель на список аргументов.  
  
 `locale`  
 Используемый языковой стандарт.  
  
 Дополнительные сведения см. в разделе [Спецификации формата](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).  
  
## <a name="return-value"></a>Возвращаемое значение  
 Функции `vsnprintf_s`, `_vsnprintf_s` и `_vsnwprintf_s` возвращают число записанных символов, не включая конечный нуль-символ, или отрицательное значение, если произошла ошибка вывода. Функция `vsnprintf_s` идентична функции `_vsnprintf_s`. Функция `vsnprintf_s` добавлена для соответствия стандарту ANSI. Функция `_vnsprintf` поддерживается для совместимости с предыдущими версиями.  
  
 Если объем памяти, необходимый для хранения данных и конечного нуль-символа, превышает `sizeOfBuffer`, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md), если только параметр `count` не имеет значение [_TRUNCATE](../../c-runtime-library/truncate.md); в этом случае запись выполняется до тех пор, пока не будет заполнен `buffer`, и возвращается значение –1. Если после обработчика недопустимых параметров выполнение приложения продолжается, эти функции устанавливают значение параметра `buffer` равным пустой строке, устанавливают для `errno` значение `ERANGE` и возвращают значение –1.  
  
 Если параметр `buffer` или `format` является пустым (`NULL`) указателем или если значение параметра `count` меньше или равно нулю, вызывается обработчик недопустимых параметров. Если продолжение выполнения разрешено, эти функции устанавливают для `errno` значение `EINVAL` и возвращают -1.  
  
### <a name="error-conditions"></a>Условия ошибок  
  
|`Condition`|Назад|`errno`|  
|-----------------|------------|-------------|  
|`buffer` равно `NULL`|-1|`EINVAL`|  
|`format` равно `NULL`|-1|`EINVAL`|  
|`count` <= 0|-1|`EINVAL`|  
|`sizeOfBuffer` слишком мал (и `count` != `_TRUNCATE`)|–1 (и `buffer` задается равным пустой строке)|`ERANGE`|  
  
## <a name="remarks"></a>Примечания  
 Каждая из этих функций принимает указатель на список аргументов, затем форматирует и записывает до `count` символов заданных данных в область памяти, на которую указывает `buffer`, затем добавляет завершающий нуль-символ.  
  
 Если параметр `count` — [_TRUNCATE](../../c-runtime-library/truncate.md), эти функции выполняют запись строки до тех пор, пока `buffer` не будет заполнен с учетом завершающего нуль-символа. Если вся строка (с учетом завершающего нуль-символа) помещается в `buffer`, эти функции возвращают количество записанных символов (не включая завершающий нуль-символ); в противном случае эти функции возвращают значение –1, что указывает на то, что произошло усечение.  
  
 Версии этих функций с суффиксом `_l` идентичны за исключением того, что они используют переданный параметр языкового стандарта вместо языкового стандарта текущего потока.  
  
> [!IMPORTANT]
>  Убедитесь, что `format` не является строкой, определяемой пользователем. Дополнительные сведения см. в разделе [Как избежать переполнения буфера](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
> [!NOTE]
>  Чтобы было достаточно места для завершающего нуль-символа, убедитесь, что значение параметра `count` строго меньше размера буфера, или используйте `_TRUNCATE`.  
  
 В C++ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера (что исключает необходимость указания аргумента с размером буфера), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами. Дополнительные сведения см. в разделе [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_vsntprintf_s`|`_vsnprintf_s`|`_vsnprintf_s`|`_vsnwprintf_s`|  
|`_vsntprintf_s_l`|`_vsnprintf_s_l`|`_vsnprintf_s_l`|`_vsnwprintf_s_l`|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательные заголовки|  
|-------------|---------------------|----------------------|  
|`vsnprintf_s`|\<stdio.h> и \<stdarg.h>|\<varargs.h>*|  
|`_vsnprintf_s`, `_vsnprintf_s_l`|\<stdio.h> и \<stdarg.h>|\<varargs.h>*|  
|`_vsnwprintf_s`, `_vsnwprintf_s_l`|\<stdio.h> или \<wchar.h> и \<stdarg.h>|\<varargs.h>*|  
  
 \* Требуется для совместимости с UNIX V.  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
```  
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
 [Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)   
 [Функции vprintf](../../c-runtime-library/vprintf-functions.md)   
 [fprintf, _fprintf_l, fwprintf, _fwprintf_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf, _printf_l, wprintf, _wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [va_arg, va_copy, va_end, va_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)