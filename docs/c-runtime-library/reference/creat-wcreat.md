---
title: "_creat _wcreat | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _creat
- _wcreat
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- wcreat
- _wcreat
- _creat
- tcreat
- _tcreat
dev_langs:
- C++
helpviewer_keywords:
- wcreat function
- _wcreat function
- files [C++], creating
- _creat function
- tcreat function
- creat function
- _tcreat function
ms.assetid: 3b3b795d-1620-40ec-bd2b-a4bbb0d20fe5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0355f28ada6313e201b8d761813767135ee3cbf8
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="creat-wcreat"></a>Функция _creat, _wcreat
Создание нового файла. Не рекомендуется использовать функции `_creat` и `_wcreat`; вместо них используйте функции [_sopen_s, _wsopen_s](../../c-runtime-library/reference/sopen-s-wsopen-s.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int _creat(   
   const char *filename,  
   int pmode   
);  
int _wcreat(   
   const wchar_t *filename,  
   int pmode   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `filename`  
 Имя нового файла.  
  
 `pmode`  
 Настройка разрешений.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Эти функции при успешном завершении возвращают дескриптор созданного файла. В противном случае функции возвращают значение -1 и задайте `errno` как показано в следующей таблице.  
  
|Значение `errno`|Описание:|  
|---------------------|-----------------|  
|`EACCES`|Параметр `filename` определяет существующий файл, доступный только для чтения, или указывает каталог вместо файла.|  
|`EMFILE`|Больше нет доступных дескрипторов файлов.|  
|`ENOENT`|Не удалось найти указанный файл.|  
  
 Если параметр `filename` имеет значение NULL, вызывается обработчик недопустимых параметров, как описано в статье [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если продолжение выполнения разрешено, эти функции устанавливают для `errno` значение `EINVAL` и возвращают -1.  
  
 Дополнительные сведения об этих и других кодах возврата см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Примечания  
 Функция `_creat` создает новый файл или открывает и обрезает существующий. `_wcreat` — это версия `_creat` с расширенными символами; аргумент `filename` для `_wcreat` — строка расширенных символов. Поведение `_wcreat` и `_creat` идентично в противном случае.  
  
### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tcreat`|`_creat`|`_creat`|`_wcreat`|  
  
 Если файл, указанный параметром `filename`, не существует, будет создан новый открытый для записи файл с заданными настройками разрешений. Если файл уже существует и его настройки разрешений допускают запись, функция `_creat` обрезает файл до длины 0, уничтожая предыдущее содержимое, и открывает его для записи. Настройка разрешений, `pmode`, применяется только к вновь созданным файлам. Новый файл получает указанные настройки разрешений после его первого закрытия. Целочисленное выражение `pmode` содержит одну или обе константы манифеста `_S_IWRITE` и `_S_IREAD`, определенные в SYS\Stat.h. Если указаны обе константы, они объединяются побитовым оператором `OR` ( **&#124;** ). Параметр `pmode` имеет одно из следующих значений.  
  
|Значение|Определение|  
|-----------|----------------|  
|`_S_IWRITE`|Разрешена запись.|  
|`_S_IREAD`|Разрешено чтение.|  
|`_S_IREAD &#124; _S_IWRITE`|Разрешены чтение и запись.|  
  
 Если разрешение на запись не предоставлено, файл остается доступным только для чтения. Все файлы всегда доступны для чтения; невозможно предоставить разрешение только на запись. Поэтому режимы `_S_IWRITE` и `_S_IREAD | _S_IWRITE` эквивалентны. Файлы, открытые с помощью функции `_creat`, всегда открываются в режиме совместимости (см. раздел [_sopen](../../c-runtime-library/reference/sopen-wsopen.md)) с `_SH_DENYNO`.  
  
 Прежде чем устанавливать разрешения, функция `_creat` применяет текущую маску разрешений файла к `pmode` (см. раздел [_umask](../../c-runtime-library/reference/umask.md)). Функция `_creat` предоставлена в основном для обеспечения совместимости с предыдущими библиотеками. Вызов функции `_open` со значениями `_O_CREAT` и `_O_TRUNC` в параметре `oflag` эквивалентен вызову функции `_creat` и предпочтителен для нового кода.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательный заголовок|  
|-------------|---------------------|---------------------|  
|`_creat`|\<io.h>|\<sys/types.h>, \<sys/stat.h>, \<errno.h>|  
|`_wcreat`|\<io.h> или \<wchar.h>|\<sys/types.h>, \<sys/stat.h>, \<errno.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
```  
// crt_creat.c  
// compile with: /W3  
// This program uses _creat to create  
// the file (or truncate the existing file)  
// named data and open it for writing.  
  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <io.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   int fh;  
  
   fh = _creat( "data", _S_IREAD | _S_IWRITE ); // C4996  
   // Note: _creat is deprecated; use _sopen_s instead  
   if( fh == -1 )  
      perror( "Couldn't create data file" );  
   else  
   {  
      printf( "Created data file.\n" );  
      _close( fh );  
   }  
}  
```  
  
```Output  
Created data file.  
```  
  
## <a name="see-also"></a>См. также  
 [Низкоуровневый ввод-вывод](../../c-runtime-library/low-level-i-o.md)   
 [_chmod, _wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [_chsize](../../c-runtime-library/reference/chsize.md)   
 [_close](../../c-runtime-library/reference/close.md)   
 [_dup, _dup2](../../c-runtime-library/reference/dup-dup2.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_sopen, _wsopen](../../c-runtime-library/reference/sopen-wsopen.md)   
 [_umask](../../c-runtime-library/reference/umask.md)