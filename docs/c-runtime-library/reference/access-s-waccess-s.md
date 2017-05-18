---
title: "_access_s, _waccess_s | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _access_s
- _waccess_s
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
- waccess_s
- access_s
- _waccess_s
- _access_s
dev_langs:
- C++
helpviewer_keywords:
- access_s function
- taccess_s function
- _taccess_s function
- waccess_s function
- _access_s function
- _waccess_s function
ms.assetid: fb3004fc-dcd3-4569-8b27-d817546e947e
caps.latest.revision: 28
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
ms.openlocfilehash: 051c2e6a6b0315e2ca4ab3192f28a370d969ec5b
ms.contentlocale: ru-ru
ms.lasthandoff: 03/30/2017

---
# <a name="accesss-waccesss"></a>_access_s, _waccess_s
Определяет разрешения на чтение и запись файлов. Это — версия функций [_access, _waccess](../../c-runtime-library/reference/access-waccess.md) с усовершенствованиями системы безопасности, описанными в разделе [Возможности безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
errno_t _access_s(   
   const char *path,   
   int mode   
);  
errno_t _waccess_s(   
   const wchar_t *path,   
   int mode   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `path`  
 Путь к файлу или каталогу.  
  
 `mode`  
 Настройка разрешений.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Если файл имеет заданный режим, все функции возвращают значение 0. Если указанный файл не существует или недоступен в заданном режиме, функция возвращает код ошибки. Код ошибки выбирается из набора описанным ниже образом и присваивает `errno` такое же значение.  
  
 `EACCES`  
 Доступ запрещен. Настройка разрешений файла не допускает указанный доступ.  
  
 `ENOENT`  
 Имя файла или путь не найдены.  
  
 `EINVAL`  
 Недопустимый параметр.  
  
 Дополнительные сведения см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Примечания  
 При использовании с файлами функция `_access_s` определяет, существует ли указанный файл и можно ли получить к нему доступ согласно значению `mode`. При использовании с каталогами функция `_access_s` определяет, существует ли указанный каталог. В [!INCLUDE[Win2kFamily](../../c-runtime-library/includes/win2kfamily_md.md)] и более поздних версиях операционной системы все каталоги имеют доступ на чтение и запись.  
  
|значение режима|Проверяет файл на|  
|----------------|---------------------|  
|00|Существование.|  
|02|Разрешение на запись.|  
|04|Разрешение на чтение.|  
|06|Разрешение на чтение и запись.|  
  
 Сами по себе разрешения на чтение или запись файла не обеспечивают возможность открывать файл. Например, если файл заблокирован другим процессом, он может оказаться недоступным, даже если `_access_s` возвращает значение 0.  
  
 `_waccess_s` — это версия `_access_s` с расширенными символами, где аргумент `path` для `_waccess_s` представляет собой строку расширенных символов. В противном случае поведение `_waccess_s` и `_access_s` идентично.  
  
 Эти функции проверяют свои параметры. Если `path` имеет значение `NULL` или `mode` не указывает действительный режим, вызывается обработчик недопустимых параметров (см. раздел [Проверка параметров](../../c-runtime-library/parameter-validation.md)). Если выполнение может быть продолжено, эти функции устанавливают параметр `errno` в значение `EINVAL` и возвращают значение `EINVAL`.  
  
### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_taccess_s`|`_access_s`|`_access_s`|`_waccess_s`|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательный заголовок|  
|-------------|---------------------|---------------------|  
|`_access_s`|\<io.h>|\<errno.h>|  
|`_waccess_s`|\<wchar.h> или \<io.h>|\<errno.h>|  
  
## <a name="example"></a>Пример  
 В этом примере для проверки файла с именем crt_access_s.на существование и возможность записи используется `_access_s`.  
  
```  
// crt_access_s.c  
  
#include <io.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
    errno_t err = 0;  
  
    // Check for existence.   
    if ((err = _access_s( "crt_access_s.c", 0 )) == 0 )  
    {  
        printf_s( "File crt_access_s.c exists.\n" );  
  
        // Check for write permission.   
        if ((err = _access_s( "crt_access_s.c", 2 )) == 0 )  
        {  
            printf_s( "File crt_access_s.c does have "  
                      "write permission.\n" );  
        }  
        else  
        {  
            printf_s( "File crt_access_s.c does not have "  
                      "write permission.\n" );  
        }  
    }  
    else  
    {  
        printf_s( "File crt_access_s.c does not exist.\n" );  
    }  
}  
```  
  
```Output  
File crt_access_s.c exists.  
File crt_access_s.c does not have write permission.  
```  
  
## <a name="see-also"></a>См. также  
 [Обработка файлов](../../c-runtime-library/file-handling.md)   
 [_access, _waccess](../../c-runtime-library/reference/access-waccess.md)   
 [_chmod, _wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [Функции _stat, _wstat](../../c-runtime-library/reference/stat-functions.md)
