---
title: "_getcwd, _wgetcwd | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wgetcwd
- _getcwd
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
- api-ms-win-crt-environment-l1-1-0.dll
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _getcwd
- wgetcwd
- _wgetcwd
- tgetcwd
- _tgetcwd
dev_langs:
- C++
helpviewer_keywords:
- getcwd function
- working directory
- _wgetcwd function
- _getcwd function
- current working directory
- wgetcwd function
- directories [C++], current working
ms.assetid: 888dc8c6-5595-4071-be55-816b38e3e739
caps.latest.revision: 24
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: ad70ffac5cbe6cc7c56dbad0930bc87b969a1857
ms.contentlocale: ru-ru
ms.lasthandoff: 04/04/2017

---
# <a name="getcwd-wgetcwd"></a>_getcwd, _wgetcwd
Получает текущий рабочий каталог.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
char *_getcwd(   
   char *buffer,  
   int maxlen   
);  
wchar_t *_wgetcwd(   
   wchar_t *buffer,  
   int maxlen   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `buffer`  
 Место хранения пути.  
  
 `maxlen`  
 Максимальная длина пути в символах: `char` для `_getcwd` и `wchar_t` для `_wgetcwd`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на `buffer`. Возвращаемое значение `NULL` указывает на ошибку, а для `errno` задается значение `ENOMEM`, указывающее на недостаток памяти для выделения `maxlen` байт (если аргумент `NULL` задан как `buffer`), или значение `ERANGE`, указывающее, что длина пути превышает `maxlen` . Если значение `maxlen` меньше или равно нулю, эта функция вызывает обработчик недопустимых параметров, как описано в разделе [Parameter Validation](../../c-runtime-library/parameter-validation.md).  
  
 Дополнительные сведения об этих и других кодах возврата см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Примечания  
 Функция `_getcwd` получает полный путь текущего рабочего каталога для диска по умолчанию и сохраняет его в параметре `buffer`. Целочисленный аргумент `maxlen` указывает максимальную длину пути. Ошибка возникает, если длина пути (включая завершающий нуль-символ) превышает `maxlen`. Аргумент `buffer` может иметь значение `NULL`. С помощью `malloc` автоматически выделяется буфер минимального размера `maxlen` (больше только при необходимости) для сохранения пути. Позже этот буфер можно освободить путем вызова `free` и передачи в него возвращаемого значения `_getcwd` (указателя на выделенный буфер).  
  
 `_getcwd` возвращает строку, представляющую путь к текущему рабочему каталогу. Если текущим рабочим каталогом является корневой каталог, строка заканчивается обратной косой чертой ( `\` ). Если текущий рабочий каталог отличается от корневого, строка заканчивается именем каталога, а не обратной косой чертой.  
  
 `_wgetcwd` — это версия с расширенными символами для `_getcwd`; аргумент `buffer` и возвращаемое значение `_wgetcwd` являются строками с расширенными символами. Поведение`_wgetcwd` и `_getcwd` идентично в противном случае.  
  
 Если определены директивы `_DEBUG` и `_CRTDBG_MAP_ALLOC` , вызовы функций `_getcwd` и `_wgetcwd` заменяются вызовами функций `_getcwd_dbg` и `_wgetcwd_dbg` , чтобы разрешить отладку выделения памяти. Дополнительные сведения см. в разделе [_getcwd_dbg, _wgetcwd_dbg](../../c-runtime-library/reference/getcwd-dbg-wgetcwd-dbg.md).  
  
### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tgetcwd`|`_getcwd`|`_getcwd`|`_wgetcwd`|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_getcwd`|\<direct.h>|  
|`_wgetcwd`|\<direct.h> или \<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Пример  
  
```  
// crt_getcwd.c  
// This program places the name of the current directory in the   
// buffer array, then displays the name of the current directory   
// on the screen. Passing NULL as the buffer forces getcwd to allocate  
// memory for the path, which allows the code to support file paths  
// longer than _MAX_PATH, which are supported by NTFS.  
  
#include <direct.h>  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char* buffer;  
  
   // Get the current working directory:   
   if( (buffer = _getcwd( NULL, 0 )) == NULL )  
      perror( "_getcwd error" );  
   else  
   {  
      printf( "%s \nLength: %d\n", buffer, strnlen(buffer) );  
      free(buffer);  
   }  
}  
```  
  
```Output  
C:\Code  
```  
  
## <a name="see-also"></a>См. также  
 [Управление каталогами](../../c-runtime-library/directory-control.md)   
 [_chdir, _wchdir](../../c-runtime-library/reference/chdir-wchdir.md)   
 [_mkdir, _wmkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)   
 [_rmdir, _wrmdir](../../c-runtime-library/reference/rmdir-wrmdir.md)
