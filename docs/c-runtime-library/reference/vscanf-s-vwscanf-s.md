---
title: "vscanf_s, vwscanf_s | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- vscanf_s
- vwscanf_s
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
apitype: DLLExport
f1_keywords:
- _vtscanf_s
- vscanf_s
- vwscanf_s
dev_langs:
- C++
ms.assetid: 23a1c383-5b01-4887-93ce-534a1e38ed93
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: e403758253afd8778f9b9c2d96f56773cf0eb44a
ms.contentlocale: ru-ru
ms.lasthandoff: 03/30/2017

---
# <a name="vscanfs-vwscanfs"></a>vscanf_s, vwscanf_s
Считывает отформатированные данные из стандартного входного потока. Это версии функций [vscanf, vwscanf](../../c-runtime-library/reference/vscanf-vwscanf.md) с усовершенствованной безопасностью, как описано в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int vscanf_s(  
   const char *format,  
   va_list arglist  
);   
int vwscanf_s(  
   const wchar_t *format,  
   va_list arglist  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `format`  
 Строка управления форматированием.  
  
 `arglist`  
 Список аргументов переменных.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает количество успешно преобразованных и назначенных полей. Возвращаемое значение не включает поля, которые были прочитаны, но не были назначены. Возвращаемое значение 0 указывает, что поля не были назначены. Значение `EOF` возвращается в случае ошибки или при обнаружении символа конца файла или конца строки при первой попытке чтения символа. Если `format` является указателем `NULL`, вызывается недопустимый обработчик параметров (см. раздел [Проверка параметров](../../c-runtime-library/parameter-validation.md)). Если выполнение может быть продолжено, то функции `vscanf_s` и `vwscanf_s` возвращают ошибку `EOF` и устанавливают для `errno` значение `EINVAL`.  
  
 Дополнительные сведения об этих и других кодах ошибок см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Примечания  
 Функция `vscanf_s` считывает данные из стандартного входного потока `stdin` и записывает эти данные в расположения, указанные списком аргументов `arglist`. Каждый аргумент в списке должен быть указателем на переменную, которая имеет тип, соответствующий спецификатору типа в параметре `format`. Если копирование производится между перекрывающимися строками, поведение не определено.  
  
 `vwscanf_s` — это версия `vscanf_s` с расширенными символами; аргумент `format` для `vwscanf_s` — строка расширенных символов. `vwscanf_s` и `vscanf_s` ведут себя одинаково, если поток открыт в режиме ANSI. `vscanf_s` не поддерживает ввод из потока ЮНИКОДА.  
  
 В отличие от `vscanf` и `vwscanf` для `vscanf_s` и `vwscanf_s` требуется указать размер буфера для всех входных параметров типа `c`, `C`, `s`, `S` или наборы элементов управления строками, заключенные в `[]`. Размер буфера в символах передается как дополнительный параметр, после которого сразу следует указатель на буфер или переменную. Размер буфера в символах для строки `wchar_t` строка не совпадает с размером в байтах.  
  
 Размер буфера включает завершающее значение NULL. Можно использовать поле спецификации ширины, чтобы гарантировать, что считываемый токен поместится в буфер. Если поле, указывающее ширину, не используется, а данные чтения токена слишком большие и не помещаются в буфер, в этот буфер ничего не записывается.  
  
> [!NOTE]
>  Параметр размера имеет тип `unsigned`, а не `size_t`.  
  
 Дополнительные сведения см. в разделе [Спецификация ширины scanf](../../c-runtime-library/scanf-width-specification.md).  
  
### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_vtscanf_s`|`vscanf_s`|`vscanf_s`|`vwscanf_s`|  
  
 Дополнительные сведения см. в разделе [Поля спецификации формата — функции scanf и wscanf](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`vscanf_s`|\<stdio.h>|  
|`wscanf_s`|\<stdio.h> или \<wchar.h>|  
  
 Консоль не поддерживается в приложениях [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]. Стандартные дескрипторы потока, связанные с консолью, `stdin`, `stdout` и `stderr`, необходимо перенаправить, чтобы функции C времени выполнения могли использовать их в приложениях [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]. Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Пример  
  
```  
// crt_vscanf_s.c  
// compile with: /W3  
// This program uses the vscanf_s and vwscanf_s functions  
// to read formatted input.  
  
#include <stdio.h>  
#include <stdarg.h>  
#include <stdlib.h>  
  
int call_vscanf_s(char *format, ...)  
{  
    int result;  
    va_list arglist;  
    va_start(arglist, format);  
    result = vscanf_s(format, arglist);  
    va_end(arglist);  
    return result;  
}  
  
int call_vwscanf_s(wchar_t *format, ...)  
{  
    int result;  
    va_list arglist;  
    va_start(arglist, format);  
    result = vwscanf_s(format, arglist);  
    va_end(arglist);  
    return result;  
}  
  
int main( void )  
{  
    int   i, result;  
    float fp;  
    char  c, s[81];  
    wchar_t wc, ws[81];  
    result = call_vscanf_s("%d %f %c %C %s %S", &i, &fp, &c, 1,  
                           &wc, 1, s, _countof(s), ws, _countof(ws) );  
    printf( "The number of fields input is %d\n", result );  
    printf( "The contents are: %d %f %c %C %s %S\n", i, fp, c, wc, s, ws);  
    result = call_vwscanf_s(L"%d %f %hc %lc %S %ls", &i, &fp, &c, 2,  
                            &wc, 1, s, _countof(s), ws, _countof(ws) );  
    wprintf( L"The number of fields input is %d\n", result );  
    wprintf( L"The contents are: %d %f %C %c %hs %s\n", i, fp, c, wc, s, ws);  
}  
  
```  
  
 Если эта программа получает входные данные, показанные в примере, она создает следующий результат:  
  
 `71 98.6 h z Byte characters`  
  
 `36 92.3 y n Wide characters`  
  
```Output  
The number of fields input is 6  
The contents are: 71 98.599998 h z Byte characters  
The number of fields input is 6  
The contents are: 36 92.300003 y n Wide characters  
```  
  
## <a name="see-also"></a>См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [printf, _printf_l, wprintf, _wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [scanf, _scanf_l, wscanf, _wscanf_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](../../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)   
 [vscanf, vwscanf](../../c-runtime-library/reference/vscanf-vwscanf.md)
