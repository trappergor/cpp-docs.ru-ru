---
title: "_write | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _write
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
f1_keywords: _write
dev_langs: C++
helpviewer_keywords:
- _write function
- write function
- files [C++], writing to
ms.assetid: 7b868c33-766f-4e1a-95a7-e8d25f0604c4
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2169415576f29f6d64d8f597da61fa65a8f7bf2d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="write"></a>_write
Записывает данные в файл.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int _write(  
   int fd,  
   const void *buffer,  
   unsigned int count   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `fd`  
 Дескриптор файла, в который записываются данные.  
  
 `buffer`  
 Записываемые данные.  
  
 `count`  
 Число байт.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Если все успешно, `_write` возвращает число фактически записанных байт. Если объем фактического места на диске меньше, чем размер буфера, который функция пытается записать на диск, происходит сбой `_write` и содержимое буфера не сбрасывается на диск. Возвращаемое значение-1 указывает на ошибку. Если передается недопустимый параметр, эта функция вызывает обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функция возвращает -1 и устанавливает для `errno` одно из трех значений: `EBADF`, которое означает, что дескриптор файла недопустим или что файл не открыт для записи; `ENOSPC`, которое означает, что на устройстве недостаточно места для выполнения операции; или `EINVAL`, которое означает, что `buffer` является пустым указателем или что для записи в файл в режиме Юникода было передано нечетное `count` байт.  
  
 Дополнительные сведения об этих и других кодах возврата см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Если файл открыт в текстовом режиме, каждый символ перевода строки заменяется символом возврата каретки - пары перевода строки в выходные данные. Эта замена не влияет на возвращаемое значение.  
  
 Если файл открыт в режиме преобразования Юникода (например, если `fd` открыт с помощью `_open` или `_sopen` и параметра режима, который включает `_O_WTEXT`, `_O_U16TEXT` или `_O_U8TEXT`, или если он открыт с помощью `fopen` и параметра режима, который включает `ccs=UNICODE`, `ccs=UTF-16LE` или `ccs=UTF-8`, или если режим изменен на режим преобразования Юникода с помощью `_setmode`), `buffer` интерпретируется как указатель на массив `wchar_t`, который содержит данные **UTF-16**. Попытка записи нечетного числа байт в этом режиме приводит к возникновению ошибки проверки параметра.  
  
## <a name="remarks"></a>Примечания  
 Функция `_write` записывает `count` байт из `buffer` в файл, связанный с `fd`. Операция записи начинается с текущего положения указателя файла (при наличии), связанного с данным файлом. Если файл открыт для добавления, операция начинается с текущего конца файла. После выполнения операции записи указатель файла увеличивается на число фактически записанных байт.  
  
 При записи в файлы, открытые в текстовом режиме, `_write` обрабатывает символ CTRL+Z как логический конец файла. При записи на устройство `_write` обрабатывает символ CTRL+Z в буфере как символ окончания вывода.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_write`|\<io.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Пример  
  
```  
// crt__write.c  
//   
// This program opens a file for output and uses _write to write  
// some bytes to the file.  
  
#include <io.h>  
#include <stdio.h>  
#include <stdlib.h>  
#include <fcntl.h>  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <errno.h>  
#include <share.h>  
  
char buffer[] = "This is a test of '_write' function";  
  
int main( void )  
{  
   int         fileHandle = 0;  
   unsigned    bytesWritten = 0;  
  
   if ( _sopen_s(&fileHandle, "write.o", _O_RDWR | _O_CREAT,  
                  _SH_DENYNO, _S_IREAD | _S_IWRITE) )  
      return -1;  
  
   if (( bytesWritten = _write( fileHandle, buffer, sizeof( buffer ))) == -1 )  
   {  
      switch(errno)  
      {  
         case EBADF:  
            perror("Bad file descriptor!");  
            break;  
         case ENOSPC:  
            perror("No space left on device!");  
            break;  
         case EINVAL:  
            perror("Invalid parameter: buffer was NULL!");  
            break;  
         default:  
            // An unrelated error occured   
            perror("Unexpected error!");  
      }  
   }  
   else  
   {  
      printf_s( "Wrote %u bytes to file.\n", bytesWritten );  
   }  
   _close( fileHandle );  
}  
```  
  
```Output  
Wrote 36 bytes to file.  
```  
  
## <a name="see-also"></a>См. также  
 [Низкоуровневый ввод-вывод](../../c-runtime-library/low-level-i-o.md)   
 [fwrite](../../c-runtime-library/reference/fwrite.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_read](../../c-runtime-library/reference/read.md)   
 [_setmode](../../c-runtime-library/reference/setmode.md)