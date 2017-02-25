---
title: "_popen, _wpopen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_popen"
  - "_wpopen"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "tpopen"
  - "popen"
  - "wpopen"
  - "_popen"
  - "_wpopen"
  - "_tpopen"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_popen - функция"
  - "_tpopen - функция"
  - "_wpopen - функция"
  - "каналы, создание"
  - "popen - функция"
  - "tpopen - функция"
  - "wpopen - функция"
ms.assetid: eb718ff2-c87d-4bd4-bd2e-ba317c3d6973
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# _popen, _wpopen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Создает канал и выполняет команду.  
  
> [!IMPORTANT]
>  Этот API невозможно использовать в приложениях, запускаемых в среде выполнения Windows.  Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
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
  
#### Параметры  
 *command*  
 Команда для выполнения.  
  
 *mode*  
 Режим возвращенного потока.  
  
## Возвращаемое значение  
 Возвращает поток, связанный с одним концом создаваемого канала.  Другой конец канала связан со стандартным вводом или стандартным выводом, порожденным командой.  Функции возвращают **NULL** при ошибке.  Если ошибкой является недопустимый параметр, например, если *command* или *mode* являются пустым указателем, или *mode* не является допустимым режимом, `errno` устанавливается значение `EINVAL`.  См. раздел Комментариев для получения сведений о допустимых режимах.  
  
 Дополнительные сведения об этих и других кодах ошибок см. в разделе [\_doserrno, errno, \_sys\_errlist и \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
## Заметки  
 Функция `_popen` создает канал и асинхронно выполняет порожденную копию процессора команд с помощью указанной строки *command*.  Символьная строка *mode* определяет требуемый тип доступа следующим образом.  
  
 **"r"**  
 Вызывающий процесс может считывать стандартный вывод порожденной команды с помощью возвращенного потока.  
  
 **"w"**  
 Вызывающий процесс может записывать в стандартный ввод порожденной команды с помощью возвращенного потока.  
  
 **"b"**  
 Открыть в бинарном режиме.  
  
 **"t"**  
 Открыть в текстовом режиме.  
  
> [!NOTE]
>  Если используется в программе Windows, функция `_popen` возвращает недопустимый указатель файла, из\-за которого программа может перестать отвечать.  `_popen` работает правильно в консольном приложении.  Для создания Windows\-приложения, которое перенаправляет ввод и вывод см. [Создание дочернего процесса с перенаправленным вводом и выводом](http://msdn.microsoft.com/library/windows/desktop/ms682499) в [!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)].  
  
 `_wpopen` — двухбайтовая версия `_popen`; аргумент *path* для `_wpopen` \- строка двухбайтовых знаков.  В остальных случаях поведение `_wpopen` и `_popen` идентично.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tpopen`|`_popen`|`_popen`|`_wpopen`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_popen`|\<stdio.h\>|  
|`_wpopen`|\<stdio.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Библиотеки  
 Все версии [библиотек времени выполнения C](../../c-runtime-library/crt-library-features.md).  
  
## Пример  
  
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
  
## Пример результатов выполнения  
 Этот результат предполагает, что существует только один файл в текущем каталоге с расширением имени файла .c.  
  
```  
 Volume in drive C is CDRIVE  
 Volume Serial Number is 0E17-1702  
  
 Directory of D:\proj\console\test1  
  
07/17/98  07:26p                   780 popen.c  
               1 File(s)            780 bytes  
                             86,597,632 bytes free  
  
Process returned 0  
```  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)   
 [\_pclose](../Topic/_pclose.md)   
 [\_pipe](../../c-runtime-library/reference/pipe.md)