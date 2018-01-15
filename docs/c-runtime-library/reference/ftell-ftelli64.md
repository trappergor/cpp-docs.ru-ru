---
title: "ftell, _ftelli64 | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ftelli64
- ftell
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
- _ftelli64
- ftell
dev_langs: C++
helpviewer_keywords:
- ftell function
- ftelli64 function
- _ftelli64 function
- file pointers [C++], getting current position
- file pointers [C++]
ms.assetid: 40149cd8-65f2-42ff-b70c-68e3e918cdd7
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: df0feee9beb2b2fc5144974f1fc06ff2b8d02b80
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ftell-ftelli64"></a>ftell, _ftelli64
Получает текущее положение указателя файла.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
long ftell(   
   FILE *stream   
);  
__int64 _ftelli64(   
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `stream`  
 Целевая структура `FILE`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Функции `ftell` и `_ftelli64` возвращают текущее положение в файле. Значение, возвращаемое `ftell` и `_ftelli64` может не отражать физическое смещение в байтах для потоков, открытых в текстовом режиме, так как в текстовом режиме производится преобразование перевода строки возврата каретки. Используйте `ftell` с `fseek` или `_ftelli64` с `_fseeki64` для возврата местоположения файла неправильно. В случае ошибки `ftell` и `_ftelli64` вызывают обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции возвращают-1 L и набор `errno` к одному из двух констант, определенных в ERRNO. З. Константа `EBADF` означает, что аргумент `stream` не является допустимым значением указателя файла или не ссылается на открытый файл. Константа `EINVAL` означает, что функции передан недопустимый аргумент `stream`. Если устройство неспособно выполнять поиск (например, терминалы и принтеры) или если `stream` не ссылается на открытый файл, возвращаемое значение не определено.  
  
 Дополнительные сведения об этих и других кодах возврата см. в разделе [_doserrno, errno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Примечания  
 `ftell` И `_ftelli64` функции получить текущее положение указателя файла (если таковые имеются), связанного с `stream`. Позиция представляется как смещение относительно начала потока.  
  
 Обратите внимание, что когда файл открыт для добавления данных, текущее положение в файле определяется последней операцией ввода-вывода, а не тем, где должна быть произведена следующая запись. Например, если файл открыт для добавления и последней операцией было чтение, положением в файле является место, где должна начинаться следующая операция чтения, а не следующая операция записи. (Если файл открыт для добавления, положение в файле перемещается в конец файла перед любой операцией записи.) Если в открытом для добавления файле еще не производилась ни одна операция ввода-вывода, то положением в файле является начало файла.  
  
 В текстовом режиме при вводе CTRL+Z интерпретируется как символ конца файла. В файлах, открытых для чтения/записи, функция `fopen` и все связанные с ней подпрограммы проверяют наличие символа CTRL+Z в конце файла и удаляют его, если это возможно. Это связано с тем, что использование сочетания функций `ftell` и `fseek` или `_ftelli64` и `_fseeki64` для перемещения в файле, который заканчивается символом CTRL+Z, может вызвать неправильное поведение функции `ftell` или `_ftelli64` рядом с концом файла.  
  
 Во время выполнения функция блокирует вызывающий поток, поэтому она потокобезопасна. Сведения о неблокирующей версии см. в описании функции `_ftell_nolock`.  
  
## <a name="requirements"></a>Требования  
  
|Функция|Обязательный заголовок|Необязательные заголовки|  
|--------------|---------------------|----------------------|  
|`ftell`|\<stdio.h>|\<errno.h>|  
|`_ftelli64`|\<stdio.h>|\<errno.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
```  
// crt_ftell.c  
// This program opens a file named CRT_FTELL.C  
// for reading and tries to read 100 characters. It  
// then uses ftell to determine the position of the  
// file pointer and displays this position.  
  
#include <stdio.h>  
  
FILE *stream;  
  
int main( void )  
{  
   long position;  
   char list[100];  
   if( fopen_s( &stream, "crt_ftell.c", "rb" ) == 0 )  
   {  
      // Move the pointer by reading data:   
      fread( list, sizeof( char ), 100, stream );  
      // Get position after read:   
      position = ftell( stream );  
      printf( "Position after trying to read 100 bytes: %ld\n",  
              position );  
      fclose( stream );  
   }  
}  
```  
  
```Output  
Position after trying to read 100 bytes: 100  
```  
  
## <a name="see-also"></a>См. также  
 [Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [fgetpos](../../c-runtime-library/reference/fgetpos.md)   
 [fseek, _fseeki64](../../c-runtime-library/reference/fseek-fseeki64.md)   
 [_lseek, _lseeki64](../../c-runtime-library/reference/lseek-lseeki64.md)