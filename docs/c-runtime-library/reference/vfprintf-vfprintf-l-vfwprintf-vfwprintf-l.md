---
title: "vfprintf, _vfprintf_l, vfwprintf, _vfwprintf_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_vfprintf_l"
  - "vfprintf"
  - "vfwprintf"
  - "_vfwprintf_l"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "vfwprintf"
  - "_vftprintf"
  - "vfprintf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_vfwprintf_l - функция"
  - "_vftprintf - функция"
  - "vfprintf - функция"
  - "_vftprintf_l - функция"
  - "vfprintf_l - функция"
  - "vftprintf_l - функция"
  - "vfwprintf_l - функция"
  - "vftprintf - функция"
  - "vfwprintf - функция"
  - "_vfprintf_l - функция"
  - "форматированный текст [C++]"
ms.assetid: 4443be50-cedf-40b2-b3e2-ff2b3af3b666
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# vfprintf, _vfprintf_l, vfwprintf, _vfwprintf_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Записывают форматированные выходные данные с помощью указателя на список аргументов. Существуют более безопасные версии этих функций; в разделе [vfprintf_s, _vfprintf_s_l, vfwprintf_s, _vfwprintf_s_l](../Topic/vfprintf_s,%20_vfprintf_s_l,%20vfwprintf_s,%20_vfwprintf_s_l.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int vfprintf(  
   FILE *stream,  
   const char *format,  
   va_list argptr   
);  
int _vfprintf_l(  
   FILE *stream,  
   const char *format,  
   locale_t locale,  
   va_list argptr   
);  
int vfwprintf(  
   FILE *stream,  
   const wchar_t *format,  
   va_list argptr   
);  
int _vfwprintf_l(  
   FILE *stream,  
   const wchar_t *format,  
   locale_t locale,  
   va_list argptr   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `stream`  
 Указатель на структуру `FILE`.  
  
 `format`  
 Спецификация формата.  
  
 `argptr`  
 Указатель на список аргументов.  
  
 `locale`  
 Используемый языковой стандарт.  
  
 Дополнительные сведения см. в разделе [спецификации формата](../Topic/Format%20Specification%20Syntax:%20printf%20and%20wprintf%20Functions.md).  
  
## <a name="return-value"></a>Возвращаемое значение  
 `vfprintf` и `vfwprintf` возвращают число записанных символов, не включая завершающий символ null или отрицательное значение, если произошла ошибка вывода. Если параметр `stream` или `format` является пустым указателем, вызывается обработчик недопустимого параметра, как описано в [проверки параметров](../../c-runtime-library/parameter-validation.md). Если продолжение выполнения разрешено, функции возвращают значение -1 и задают для `errno` значение `EINVAL`.  
  
 Сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
## <a name="remarks"></a>Заметки  
 Каждая из этих функций принимает указатель на список аргументов, а затем форматирует и записывает заданных данных в `stream`.  
  
 `vfwprintf` представляет версию расширенных символов `vfprintf`; две функции ведут себя одинаково при открытии потока в режиме ANSI. `vfprintf` не поддерживает выходные данные в поток в кодировке ЮНИКОД.  
  
 Версии этих функций с суффиксом `_l` идентичны за исключением того, что они используют переданный параметр языкового стандарта вместо языкового стандарта текущего потока.  
  
> [!IMPORTANT]
>  Убедитесь, что `format` не является строкой, определяемой пользователем. Дополнительные сведения см. в разделе [как избежать переполнения буфера](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_vftprintf`|`vfprintf`|`vfprintf`|`vfwprintf`|  
|`_vftprintf_l`|`_vfprintf_l`|`_vfprintf_l`|`_vfwprintf_l`|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательные заголовки|  
|-------------|---------------------|----------------------|  
|`vfprintf`, _`vfprintf_l`|\<stdio.h> и \<stdarg.h>|\<varargs.h>*|  
|`vfwprintf`, _`vfwprintf_l`|\<stdio.h> или \<wchar.h> и \<stdarg.h>|\<varargs.h>*|  
  
 \* Необходим для совместимости UNIX V.  
  
 Дополнительные сведения о совместимости, в разделе [совместимости](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="net-framework-equivalent"></a>Эквивалент .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [примеры вызова неуправляемого кода платформы](../Topic/Platform%20Invoke%20Examples.md).  
  
## <a name="see-also"></a>См. также  
 [Поток ввода-вывода](../../c-runtime-library/stream-i-o.md)   
 [Функции vprintf](../../c-runtime-library/vprintf-functions.md)   
 [fprintf, _fprintf_l, fwprintf, _fwprintf_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf, _printf_l, wprintf, _wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [va_arg, va_copy, va_end, va_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)