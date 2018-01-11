---
title: "vsscanf_s, vswscanf_s | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- vswscanf_s
- vsscanf_s
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
- vsscanf_s
- vswscanf_s
- _vstscanf_s
dev_langs: C++
ms.assetid: 7b732e68-c6f4-4579-8917-122f5a7876e1
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b041da3df2b745f1764440ed5afafa2cd7690b68
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="vsscanfs-vswscanfs"></a>vsscanf_s, vswscanf_s
Считывают форматированные данные из строки. Это версии функций [sscanf, vswscanf](../../c-runtime-library/reference/vsscanf-vswscanf.md) с усовершенствованной безопасностью, как описано в разделе [Усовершенствования безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int vsscanf_s(  
   const char *buffer,  
   const char *format,  
   va_list argptr  
);   
int vswscanf_s(  
   const wchar_t *buffer,  
   const wchar_t *format,  
   va_list arglist  
);   
```  
  
#### <a name="parameters"></a>Параметры  
 `buffer`  
 Сохраненные данные  
  
 `format`  
 Строка управления форматом. Дополнительные сведения см. в разделе [Поля спецификации формата — функции scanf и wscanf](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md).  
  
 `arglist`  
 Список аргументов переменных.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Каждая из этих функций возвращает количество полей, которые были успешно преобразованы и присвоены; возвращаемое значение не включает поля, которые были считаны, но не были присвоены. Возвращаемое значение 0 указывает, что поля не были назначены. Если до первого преобразования возникает ошибка или достигается конец строки, возвращается значение `EOF`.  
  
 Если `buffer` или `format` является указателем `NULL`, вызывается обработчик недопустимых параметров, как описано в статье [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если разрешается продолжать выполнение, эти функции возвращают -1 и присваивают `errno` значение `EINVAL`.  
  
 Дополнительные сведения об этих и других кодах ошибок см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Примечания  
 Функция `vsscanf_s` считывает данные из `buffer` в расположения, указанные аргументами в списке аргументов `arglist`. Аргументы в списке аргументов задают указатели на переменные, имеющие тип, соответствующий спецификатору типа в `format`. В отличие от менее безопасной версии `vsscanf`, требуется параметр размера буфера при использовании символов полей типа `c`, `C`, `s`, `S` или наборов элементов управления строк, заключенных в `[]`. Размер буфера в символах должен указываться как дополнительный параметр сразу после каждого параметра буфера, которому он требуется.  
  
 Размер буфера включает завершающее значение NULL. Можно использовать поле спецификации ширины, чтобы гарантировать, что считываемый токен поместится в буфер. Если поле, указывающее ширину, не используется, а данные чтения токена слишком большие и не помещаются в буфер, в этот буфер ничего не записывается.  
  
 Дополнительные сведения см. в разделах [scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](../../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md) и [Символы поля типа scanf](../../c-runtime-library/scanf-type-field-characters.md).  
  
> [!NOTE]
>  Параметр размера имеет тип `unsigned`, а не `size_t`.  
  
 Аргумент `format` определяет интерпретацию полей входных данных и имеет такую же форму и функцию, как аргумент `format` для функции `scanf_s`. Если копирование производится между перекрывающимися строками, поведение не определено.  
  
 `vswscanf_s` — это двухбайтовая версия `vsscanf_s`; аргументы для `vswscanf_s` представляют собой двухбайтовые строки. `vsscanf_s` не обрабатывает многобайтовые шестнадцатеричные символы. `vswscanf_s` не обрабатывает шестнадцатеричные символы Юникода полной ширины и символы "зоны совместимости". В противном случае поведение `vswscanf_s` и `vsscanf_s` идентично.  
  
### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_vstscanf_s`|`vsscanf_s`|`vsscanf_s`|`vswscanf_s`|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`vsscanf_s`|\<stdio.h>|  
|`vswscanf_s`|\<stdio.h> или \<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Пример  
  
```  
// crt_vsscanf_s.c  
// compile with: /W3  
// This program uses vsscanf_s to read data items  
// from a string named tokenstring, then displays them.  
  
#include <stdio.h>  
#include <stdarg.h>  
#include <stdlib.h>  
  
int call_vsscanf_s(char *tokenstring, char *format, ...)  
{  
    int result;  
    va_list arglist;  
    va_start(arglist, format);  
    result = vsscanf_s(tokenstring, format, arglist);  
    va_end(arglist);  
    return result;  
}  
  
int main( void )  
{  
    char  tokenstring[] = "15 12 14...";  
    char  s[81];  
    char  c;  
    int   i;  
    float fp;  
  
    // Input various data from tokenstring:  
    // max 80 character string:  
    call_vsscanf_s(tokenstring, "%80s", s, _countof(s));  
    call_vsscanf_s(tokenstring, "%c", &c, sizeof(char));  
    call_vsscanf_s(tokenstring, "%d", &i);  
    call_vsscanf_s(tokenstring, "%f", &fp);  
  
    // Output the data read  
    printf("String    = %s\n", s);  
    printf("Character = %c\n", c);  
    printf("Integer:  = %d\n", i);  
    printf("Real:     = %f\n", fp);  
}  
```  
  
```Output  
String    = 15  
Character = 1  
Integer:  = 15  
Real:     = 15.000000  
```  
  
## <a name="see-also"></a>См. также  
 [Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)   
 [scanf, _scanf_l, wscanf, _wscanf_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sscanf, _sscanf_l, swscanf, _swscanf_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)   
 [sscanf_s, _sscanf_s_l, swscanf_s, _swscanf_s_l](../../c-runtime-library/reference/sscanf-s-sscanf-s-l-swscanf-s-swscanf-s-l.md)   
 [sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [vsscanf, vswscanf](../../c-runtime-library/reference/vsscanf-vswscanf.md)