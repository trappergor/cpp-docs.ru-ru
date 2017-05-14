---
title: "_locking | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _locking
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
- _locking
dev_langs:
- C++
helpviewer_keywords:
- locking function
- bytes [C++], locking file
- files [C++], locking bytes
- files [C++], locking
- _locking function
ms.assetid: 099aaac1-d4ca-4827-aed6-24dff9844150
caps.latest.revision: 19
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
ms.openlocfilehash: 7789a1634f5ee87d54d6b9f2aadbc720819f31ef
ms.contentlocale: ru-ru
ms.lasthandoff: 04/01/2017

---
# <a name="locking"></a>_locking
Блокирует или разблокирует байт файла.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      int _locking(  
   int fd,  
   int mode,  
   long nbytes   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `fd`  
 Дескриптор файла.  
  
 *mode*  
 Выполняемое действие блокировки.  
  
 *nbytes*  
 Число байтов для блокировки.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Функция `_locking` возвращает 0 в случае успеха. Возвращаемое значение -1, указывающее на ошибку, в этом случае [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) присваивается одно из следующих значений.  
  
 `EACCES`  
 Нарушение блокировки (файл уже заблокирован или разблокирован).  
  
 `EBADF`  
 Недопустимый дескриптор файла.  
  
 `EDEADLOCK`  
 Нарушение блокировки. Возвращается, если указан флаг `_LK_LOCK` или `_LK_RLCK` и файл не может быть заблокирован после 10 попыток.  
  
 `EINVAL`  
 В функцию `_locking` передан недопустимый аргумент.  
  
 Если сбой происходит из-за недопустимого параметра, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  
  
## <a name="remarks"></a>Примечания  
 Функция `_locking` блокирует или разблокирует *nbytes* байт из файла, указанного в `fd`. Блокировка байтов в файле предотвращает доступ других процессов к этим байтам. Все блокировки или разблокировки начинаются с текущего положения указателя файла и распространяются на следующие *nbytes* байт. Возможна блокировка байтов за концом файла.  
  
 Параметр *mode* должен быть одной из следующих констант манифеста, определенных в файле Locking.h.  
  
 `_LK_LOCK`  
 Блокирует указанные байты. Если заблокировать байты не удается, программа попытается повторить блокировку через 1 секунду. Если после 10 попыток байты все равно не удается заблокировать, константа возвращает ошибку.  
  
 `_LK_NBLCK`  
 Блокирует указанные байты. Если после 10 попыток байты все равно не удается заблокировать, константа возвращает ошибку.  
  
 `_LK_NBRLCK`  
 Эквивалентно `_LK_NBLCK`.  
  
 `_LK_RLCK`  
 Эквивалентно `_LK_LOCK`.  
  
 `_LK_UNLCK`  
 Разблокирует указанные байты, которые предварительно должны быть заблокированы.  
  
 Можно заблокировать несколько разделов файла, которые не перекрываются. Разблокируемый раздел файла должен быть предварительно заблокирован. Функция `_locking` не объединяет смежные разделы. Если два заблокированных раздела являются смежными, каждый из них должен быть разблокирован отдельно. Разделы следует блокировать только на короткое время. Их необходимо разблокировать перед закрытием файла или выходом из программы.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательный заголовок|  
|-------------|---------------------|---------------------|  
|`_locking`|\<io.h> и \<sys/locking.h>|\<errno.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="libraries"></a>Библиотеки  
 Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Пример  
  
```  
// crt_locking.c  
/* This program opens a file with sharing. It locks  
 * some bytes before reading them, then unlocks them. Note that the  
 * program works correctly only if the file exists.  
 */  
  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <sys/locking.h>  
#include <share.h>  
#include <fcntl.h>  
#include <stdio.h>  
#include <stdlib.h>  
#include <io.h>  
  
int main( void )  
{  
   int  fh, numread;  
   char buffer[40];  
  
   /* Quit if can't open file or system doesn't   
    * support sharing.   
    */  
   errno_t err = _sopen_s( &fh, "crt_locking.txt", _O_RDONLY, _SH_DENYNO,   
                          _S_IREAD | _S_IWRITE );  
   printf( "%d %d\n", err, fh );  
   if( err != 0 )  
      exit( 1 );  
  
   /* Lock some bytes and read them. Then unlock. */  
   if( _locking( fh, LK_NBLCK, 30L ) != -1 )  
   {  
      long lseek_ret;  
      printf( "No one can change these bytes while I'm reading them\n" );  
      numread = _read( fh, buffer, 30 );  
      buffer[30] = '\0';  
      printf( "%d bytes read: %.30s\n", numread, buffer );  
      lseek_ret = _lseek( fh, 0L, SEEK_SET );  
      _locking( fh, LK_UNLCK, 30L );  
      printf( "Now I'm done. Do what you will with them\n" );  
   }  
   else  
      perror( "Locking failed\n" );  
  
   _close( fh );  
}  
```  
  
## <a name="input-crtlockingtxt"></a>Входные данные: crt_locking.txt  
  
```  
The first thirty bytes of this file will be locked.  
```  
  
## <a name="sample-output"></a>Пример результатов выполнения  
  
```  
No one can change these bytes while I'm reading them  
30 bytes read: The first thirty bytes of this  
Now I'm done. Do what you will with them  
```  
  
## <a name="see-also"></a>См. также  
 [Обработка файлов](../../c-runtime-library/file-handling.md)   
 [_creat, _wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)
