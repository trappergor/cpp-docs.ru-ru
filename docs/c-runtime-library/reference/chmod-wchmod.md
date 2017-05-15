---
title: "_chmod _wchmod | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _chmod
- _wchmod
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _chmod
- _wchmod
- wchmod
dev_langs:
- C++
helpviewer_keywords:
- _chmod function
- wchmod function
- file permissions [C++]
- chmod function
- files [C++], changing permissions
- _wchmod function
ms.assetid: 92f7cb86-b3b0-4232-a599-b8c04a2f2c19
caps.latest.revision: 23
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: c0db1569ea6a90892b7eb3d0d8f08f3c9fcf7115
ms.contentlocale: ru-ru
ms.lasthandoff: 04/04/2017

---
# <a name="chmod-wchmod"></a>_chmod, _wchmod
Изменяет параметры разрешений файла.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      int _chmod(   
   const char *filename,  
   int pmode   
);  
int _wchmod(   
   const wchar_t *filename,  
   int pmode   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `filename`  
 Имя существующего файла.  
  
 `pmode`  
 Настройка разрешений для файла.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Эти функции возвращают 0, если параметр разрешений успешно изменен. Возвращаемое значение-1 означает сбой. Если указанный файл не найден, `errno` принимает значение `ENOENT`; если параметр является допустимым, `errno` принимает значение `EINVAL`.  
  
## <a name="remarks"></a>Примечания  
 `_chmod` Функция изменяет настройки разрешений файла, указанного `filename`. Параметр разрешений управляет чтением и записью в файл. Целочисленное выражение `pmode` содержит одну или обе из следующих констант манифеста, определенных в файле SYS\Stat.h.  
  
 `_S_IWRITE`  
 Разрешена запись.  
  
 `_S_IREAD`  
 Разрешено чтение.  
  
 `_S_IREAD | _S_IWRITE`  
 Разрешены чтение и запись.  
  
 Если указаны обе константы, они объединяются побитовым оператором `OR` (`|`). Если разрешение на запись не предоставлено, файл остается доступным только для чтения. Обратите внимание на то, что все файлы всегда доступны для чтения; предоставить разрешение только на запись нельзя. Таким образом, режимы `_S_IWRITE` и `_S_IREAD | _S_IWRITE` эквивалентны.  
  
 `_wchmod` — это версия `_chmod` с расширенными символами; аргумент `filename` для `_wchmod` — строка расширенных символов. Поведение `_wchmod` и `_chmod` идентично в противном случае.  
  
 Эта функция проверяет свои параметры. Если `pmode` не является комбинацией одной из констант манифеста и не включает дополнительный набор констант, функция просто их пропускает. Если параметр `filename` имеет значение `NULL`, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, параметр `errno` устанавливается в значение `EINVAL` и функция возвращает –1.  
  
### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tchmod`|`_chmod`|`_chmod`|`_wchmod`|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательный заголовок|  
|-------------|---------------------|---------------------|  
|`_chmod`|\<io.h>|\<sys/types.h>, \<sys/stat.h>, \<errno.h>|  
|`_wchmod`|\<io.h> или \<wchar.h>|\<sys/types.h>, \<sys/stat.h>, \<errno.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
```  
// crt_chmod.c  
// This program uses _chmod to  
// change the mode of a file to read-only.  
// It then attempts to modify the file.  
//  
  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <io.h>  
#include <stdio.h>  
#include <stdlib.h>  
#include <errno.h>  
  
// Change the mode and report error or success   
void set_mode_and_report(char * filename, int mask)  
{  
   // Check for failure   
   if( _chmod( filename, mask ) == -1 )  
   {  
      // Determine cause of failure and report.   
      switch (errno)  
      {  
         case EINVAL:  
            fprintf( stderr, "Invalid parameter to chmod.\n");  
            break;  
         case ENOENT:  
            fprintf( stderr, "File %s not found\n", filename );  
            break;  
         default:  
            // Should never be reached   
            fprintf( stderr, "Unexpected error in chmod.\n" );  
       }  
   }  
   else  
   {  
      if (mask == _S_IREAD)  
        printf( "Mode set to read-only\n" );  
      else if (mask & _S_IWRITE)  
        printf( "Mode set to read/write\n" );  
   }  
   fflush(stderr);  
}  
  
int main( void )  
{   
  
   // Create or append to a file.   
   system( "echo /* End of file */ >> crt_chmod.c_input" );  
  
   // Set file mode to read-only:   
   set_mode_and_report("crt_chmod.c_input ", _S_IREAD );  
  
   system( "echo /* End of file */ >> crt_chmod.c_input " );  
  
   // Change back to read/write:   
   set_mode_and_report("crt_chmod.c_input ", _S_IWRITE );  
  
   system( "echo /* End of file */ >> crt_chmod.c_input " );   
}   
```  
  
```Output  
  
A line of text.  
  
```  
  
```Output  
  
      A line of text.Mode set to read-only  
Access is denied.  
Mode set to read/write  
```  
  
## <a name="see-also"></a>См. также  
 [Обработка файлов](../../c-runtime-library/file-handling.md)   
 [_access, _waccess](../../c-runtime-library/reference/access-waccess.md)   
 [_creat, _wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [Функции _stat, _wstat](../../c-runtime-library/reference/stat-functions.md)
