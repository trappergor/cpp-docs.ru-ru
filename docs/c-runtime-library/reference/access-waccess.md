---
title: "_access _waccess | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _access
- _waccess
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
- _waccess
- _access
- taccess
- waccess
- _taccess
dev_langs:
- C++
helpviewer_keywords:
- access function
- _taccess function
- waccess function
- _access function
- _waccess function
- taccess function
ms.assetid: ba34f745-85c3-49e5-a7d4-3590bd249dd3
caps.latest.revision: 27
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: d0968ec14a43cfbbf1169f34ac929435787bc349
ms.contentlocale: ru-ru
ms.lasthandoff: 04/01/2017

---
# <a name="access-waccess"></a>_access, _waccess
Определяет, доступен ли файл только для чтения или нет. Существуют более безопасные версии этих функций; см. раздел [_access_s, _waccess_s](../../c-runtime-library/reference/access-s-waccess-s.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int _access(   
   const char *path,   
   int mode   
);  
int _waccess(   
   const wchar_t *path,   
   int mode   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `path`  
 Путь к файлу или каталогу.  
  
 `mode`  
 Атрибут чтения и записи.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Если файл имеет заданный режим, все функции возвращают значение 0. Функция возвращает -1, если файл с именем не существует или не имеет заданный режим; в этом случае `errno` установлено, как показано в следующей таблице.  
  
 `EACCES`  
 Доступ запрещен: настройка разрешений файла не допускает указанный доступ.  
  
 `ENOENT`  
 Имя файла или путь не найдены.  
  
 `EINVAL`  
 Недопустимый параметр.  
  
 Дополнительные сведения об этих и других кодах возврата см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Примечания  
 При использовании с файлами функция `_access` определяет, существует ли указанный файл или каталог и имеет ли он атрибуты, указанные в значении `mode`. При использовании с каталогами функция `_access` определяет, существует ли указанный каталог существует; в [!INCLUDE[Win2kFamily](../../c-runtime-library/includes/win2kfamily_md.md)] и более поздних версиях операционной системы все каталоги имеют доступ чтение и запись.  
  
|Значение `mode`|Проверяет файл на|  
|------------------|---------------------|  
|00|Существование|  
|02|Только на запись|  
|04|Только чтение|  
|06|Чтение и запись|  
  
 Эта функция проверяет только то, является ли файл или каталог доступным только для чтения; параметры безопасности файловой системы не проверяются. Для этого требуется токен доступа. Дополнительные сведения о безопасности файловой системы см. в разделе [Токены доступа](http://msdn.microsoft.com/library/windows/desktop/aa374909). Для использования этой функции предназначен класс ATL, см. раздел [Класс CAccessToken](../../atl/reference/caccesstoken-class.md).  
  
 `_waccess` — это версия `_access` с расширенными символами; аргумент `path` для `_waccess` — строка расширенных символов. Поведение `_waccess` и `_access` идентично в противном случае.  
  
 Эта функция проверяет свои параметры. Если `path` имеет значение `NULL` или `mode` не указывает действительный режим, вызывается обработчик недопустимых параметров (см. раздел [Проверка параметров](../../c-runtime-library/parameter-validation.md)). Если выполнение может быть продолжено, функция устанавливает параметр `errno` в значение `EINVAL` и возвращает –1.  
  
### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_taccess`|`_access`|`_access`|`_waccess`|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательные заголовки|  
|-------------|---------------------|----------------------|  
|`_access`|\<io.h>|\<errno.h>|  
|`_waccess`|\<wchar.h> или \<io.h>|\<errno.h>|  
  
## <a name="example"></a>Пример  
 В следующем примере для проверки файла с именем crt_ACCESS.C на существование и возможность записи используется `_access`.  
  
```  
// crt_access.c  
// compile with: /W1  
// This example uses _access to check the file named  
// crt_ACCESS.C to see if it exists and if writing is allowed.  
  
#include  <io.h>  
#include  <stdio.h>  
#include  <stdlib.h>  
  
int main( void )  
{  
    // Check for existence.  
    if( (_access( "crt_ACCESS.C", 0 )) != -1 )  
    {  
        printf_s( "File crt_ACCESS.C exists.\n" );  
  
        // Check for write permission.  
        // Assume file is read-only.  
        if( (_access( "crt_ACCESS.C", 2 )) == -1 )  
            printf_s( "File crt_ACCESS.C does not have write permission.\n" );  
    }  
}  
```  
  
```Output  
File crt_ACCESS.C exists.  
File crt_ACCESS.C does not have write permission.  
```  
  
## <a name="see-also"></a>См. также  
 [Обработка файлов](../../c-runtime-library/file-handling.md)   
 [_chmod, _wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [Функции _stat, _wstat](../../c-runtime-library/reference/stat-functions.md)
