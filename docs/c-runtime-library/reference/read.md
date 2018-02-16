---
title: "_read | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _read
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
- _read
dev_langs:
- C++
helpviewer_keywords:
- data [CRT]
- _read function
- read function
- data [C++], reading
- reading data [C++]
- files [C++], reading
ms.assetid: 2ce9c433-57ad-47fe-9ac1-4a7d4c883d30
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0ad5b18300ec36cc55a6eb02476b454829193cd8
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="read"></a>_read

Считывает данные из файла.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int _read(  
   int fd,  
   void *buffer,  
   unsigned int count   
);  
```  
  
### <a name="parameters"></a>Параметры  

*fd*  
Дескриптор файла, ссылающийся на открытый файл.  
  
*buffer*  
Место хранения данных.  
  
*count*  
Максимальное количество байтов.  
  
## <a name="return-value"></a>Возвращаемое значение  

`_read` Возвращает число байтов, чтение, которое может быть меньше, чем *число* Если доступно менее *число* слева байт в файле или если файл был открыт в текстовом режиме, в этом случае каждый возврат каретки-строки перевода пары `\r\n` заменить один символ перевода строки `\n`. Только один символ перевода строки учитывается в возвращаемом значении. Эта замена не влияет на указатель файла.  
  
Если функция пытается прочитать конечную часть файла, она возвращает 0. Если *fd* — не является допустимым, файл не открыт для чтения, или файл заблокирован, вызывается обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функция возвращает -1 и устанавливает `errno` в значение `EBADF`.  
  
Если параметр *buffer* имеет значение **NULL**, вызывается обработчик недопустимых параметров. Если продолжение выполнения разрешено, функция возвращает значение −1 и задает для `errno` значение `EINVAL`.  
  
Дополнительные сведения об этом и других кодах возврата см. в статье [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Примечания  

`_read` Функция считывает максимальное количество *число* байтов в *буфера* из файла, связанного с *fd*. Операция чтения начинается с текущего положения указателя файла, связанного с данным файлом. После операции чтения указатель файла указывает на следующий непрочитанный символ.  
  
Если файл был открыт в текстовом режиме, чтение завершается, когда `_read` встречает символ CTRL + Z, который интерпретируется как индикатор конца файла. Чтобы очистить индикатор конца файла, следует использовать [_lseek](../../c-runtime-library/reference/lseek-lseeki64.md).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_read`|\<io.h>|  
  
Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Библиотеки  

Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Пример  
  
```C  
// crt_read.c  
/* This program opens a file named crt_read.txt  
 * and tries to read 60,000 bytes from  
 * that file using _read. It then displays the  
 * actual number of bytes read.  
 */  
  
#include <fcntl.h>      /* Needed only for _O_RDWR definition */  
#include <io.h>  
#include <stdlib.h>  
#include <stdio.h>  
#include <share.h>  
  
char buffer[60000];  
  
int main( void )  
{  
   int fh;  
   unsigned int nbytes = 60000, bytesread;  
  
   /* Open file for input: */  
   if( _sopen_s( &fh, "crt_read.txt", _O_RDONLY, _SH_DENYNO, 0 ) )  
   {  
      perror( "open failed on input file" );  
      exit( 1 );  
   }  
  
   /* Read in input: */  
   if( ( bytesread = _read( fh, buffer, nbytes ) ) <= 0 )  
      perror( "Problem reading file" );  
   else  
      printf( "Read %u bytes from file\n", bytesread );  
  
   _close( fh );  
}  
```  
  
### <a name="input-crtreadtxt"></a>Входные данные: crt_read.txt  
  
```  
Line one.  
Line two.  
```  
  
### <a name="output"></a>Вывод  
  
```  
Read 19 bytes from file  
```  
  
## <a name="see-also"></a>См. также  

[Низкоуровневый ввод-вывод](../../c-runtime-library/low-level-i-o.md)   
[_creat, _wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
[fread](../../c-runtime-library/reference/fread.md)   
[_open, _wopen](../../c-runtime-library/reference/open-wopen.md)   
[_write](../../c-runtime-library/reference/write.md)
