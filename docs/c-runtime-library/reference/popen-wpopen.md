---
title: "_popen, _wpopen | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _popen
- _wpopen
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
- tpopen
- popen
- wpopen
- _popen
- _wpopen
- _tpopen
dev_langs: C++
helpviewer_keywords:
- tpopen function
- pipes, creating
- _popen function
- _tpopen function
- popen function
- wpopen function
- _wpopen function
ms.assetid: eb718ff2-c87d-4bd4-bd2e-ba317c3d6973
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 73c9e19556857c78a530f0a2ac89580ea3fec69c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="popen-wpopen"></a>_popen, _wpopen
Создает канал и выполняет команду.  
  
> [!IMPORTANT]
>  Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Синтаксис  
  
```
FILE *_popen(
const char *command,
const char *mode
);
FILE *_wpopen(
const wchar_t *command,
const wchar_t *mode
);
```  
  
#### <a name="parameters"></a>Параметры  
 *command*  
 Команда для выполнения.  
  
 *mode*  
 Режим возвращенного потока.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает поток, связанный с одним концом созданного канала. Другой конец канала связан со стандартным инициированным потоком ввода и вывода команд. Эти функции возвращают значение **NULL** при возникновении ошибки. Если ошибка возникла по причине недопустимого параметра, например, если параметр *command* или *mode* является пустым указателем или для параметра *mode* указан недопустимый режим, то для `errno` задается значение `EINVAL`. Сведения о допустимых режимах см. в разделе "Примечания".  
  
 Дополнительные сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Примечания  
 Функция`_popen` создает канал и асинхронно выполняет инициируемую копию обработчика команд с указанной строкой *command*. Строка символов *mode* определяет запрошенный тип доступа, как показано ниже.  
  
 **"r"**  
 Вызывающий процесс может считывать инициируемый поток вывода команд с помощью возвращенного потока.  
  
 **"w"**  
 Вызывающий процесс может записывать инициируемый поток ввода команд с помощью возвращенного потока.  
  
 **"b"**  
 Открыть в двоичном режиме.  
  
 **"t"**  
 Открыть в текстовом режиме.  
  
> [!NOTE]
>  При использовании в программе Windows функция `_popen` возвращает недопустимый указатель на файл, в результате чего программа перестает отвечать на запросы в течение неограниченного времени. Функция `_popen` работает соответствующим образом в консольном приложении. Создание приложения Windows, которое перенаправляет ввод и вывод — [Создание дочерний процесс с перенаправление входных и выходных данных](http://msdn.microsoft.com/library/windows/desktop/ms682499) в Windows SDK.  
  
 `_wpopen` — это версия `_popen` с расширенными символами; аргумент *path* для `_wpopen` — строка расширенных символов. Поведение `_wpopen` и `_popen` идентично в противном случае.  
  
### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tpopen`|`_popen`|`_popen`|`_wpopen`|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_popen`|\<stdio.h>|  
|`_wpopen`|\<stdio.h> или \<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Библиотеки  
 Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Пример  
  
```  
// crt_popen.c  
/* This program uses _popen and _pclose to receive a   
 * stream of text from a system process.  
 */  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
  
   char   psBuffer[128];  
   FILE   *pPipe;  
  
        /* Run DIR so that it writes its output to a pipe. Open this  
         * pipe with read text attribute so that we can read it   
         * like a text file.   
         */  
  
   if( (pPipe = _popen( "dir *.c /on /p", "rt" )) == NULL )  
      exit( 1 );  
  
   /* Read pipe until end of file, or an error occurs. */  
  
   while(fgets(psBuffer, 128, pPipe))  
   {  
      printf(psBuffer);  
   }  
  
   /* Close pipe and print return value of pPipe. */  
   if (feof( pPipe))  
   {  
     printf( "\nProcess returned %d\n", _pclose( pPipe ) );  
   }  
   else  
   {  
     printf( "Error: Failed to read the pipe to the end.\n");  
   }  
}  
```  
  
## <a name="sample-output"></a>Пример результатов выполнения  
 Эти выходные данные предполагают, что в текущем каталоге находится только один файл с расширением имени файла .c.  
  
```  
 Volume in drive C is CDRIVE  
 Volume Serial Number is 0E17-1702  
  
 Directory of D:\proj\console\test1  
  
07/17/98  07:26p                   780 popen.c  
               1 File(s)            780 bytes  
                             86,597,632 bytes free  
  
Process returned 0  
```  
  
## <a name="see-also"></a>См. также  
 [Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)   
 [_pclose](../../c-runtime-library/reference/pclose.md)   
 [_pipe](../../c-runtime-library/reference/pipe.md)
