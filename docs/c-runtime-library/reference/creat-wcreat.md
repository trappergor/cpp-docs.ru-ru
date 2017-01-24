---
title: "Функция _creat, _wcreat | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_creat"
  - "_wcreat"
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
  - "wcreat"
  - "_wcreat"
  - "_creat"
  - "tcreat"
  - "_tcreat"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Функция wcreat"
  - "Функция _wcreat"
  - "файлы [C++], создание"
  - "Функция _creat"
  - "Функция tcreat"
  - "Функция creat"
  - "Функция _tcreat"
ms.assetid: 3b3b795d-1620-40ec-bd2b-a4bbb0d20fe5
caps.latest.revision: 21
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Функция _creat, _wcreat
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Создает новый файл.  `_creat` и `_wcreat` не рекомендуется использовать; вместо этого используйте [\_sopen\_s, \_wsopen\_s](../../c-runtime-library/reference/sopen-s-wsopen-s.md).  
  
## Синтаксис  
  
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
  
#### Параметры  
 `filename`  
 Имя нового файла.  
  
 `pmode`  
 Параметры разрешений  
  
## Возвращаемое значение  
 Эти функции при успешном завершении возвращают дескриптор созданного файла.  В противном случае функции возвращают –1 и устанавливают `errno`, как показано в следующей таблице.  
  
|Значение `errno`|Описание|  
|----------------------|--------------|  
|`EACCES`|`filename` определяет существующий файл, доступный только для чтения, или указывает каталог вместо файла.|  
|`EMFILE`|Больше нет доступных дескрипторов файла.|  
|`ENOENT`|Не удалось найти указанный файл.|  
  
 Если `filename` имеет значение NULL, эти функции вызывают обработчик недопустимого параметра, как описано в [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эти функции устанавливают для `errno` значение `EINVAL` и возвращают \-1.  
  
 Дополнительные сведения об этих и других кодах возврата см. в разделе [\_doserrno, errno, \_sys\_errlist и \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
## Заметки  
 Функция `_creat` создает новый файл или открывает и обрезает существующий.  `_wcreat` — двухбайтовая версия `_creat`; аргумент `filename` для `_wcreat` \- строка двухбайтовых знаков.  В остальных случаях поведение `_wcreat` и `_creat` идентично.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tcreat`|`_creat`|`_creat`|`_wcreat`|  
  
 Если файл, указанный `filename`, не существует, то будет создан новый открытый для записи файл с заданными настройками разрешений.  Если файл уже существует и его настройки разрешений позволяют запись, `_creat` обрезает файл до длины 0, уничтожая предыдущее содержимое, и открывает его для записи.  Настройки разрешений, `pmode`, применяются только к вновь созданным файлам.  Новый файл получает определенные настройки разрешений после его закрытия в первый раз.  `pmode` это целочисленное выражение, которое содержит одну или обе константы манифестов `_S_IWRITE` и `_S_IREAD`, определенных в SYS\\Stat.h.  Если предоставлены обе константы, они объединяются битовым оператором `OR` \(  **&#124;**\).  В этом случае параметр `pmode` имеет одно из следующих значений.  
  
|Значение|Определение|  
|--------------|-----------------|  
|`_S_IWRITE`|Запись разрешена.|  
|`_S_IREAD`|Чтение разрешено.|  
|`_S_IREAD &#124; _S_IWRITE`|Чтение и запись разрешены.|  
  
 Если разрешение записи не задано, то файл доступен только для чтения.  Все файлы всегда можно читать; невозможно предоставить разрешение только на запись.  Тогда режимы `_S_IWRITE` и `_S_IREAD``| _S_IWRITE` эквивалентны.  Файлы, открытые с помощью `_creat` всегда открыты в режиме совместимости \(см. [\_sopen](../../c-runtime-library/reference/sopen-wsopen.md)\) с `_SH_DENYNO`.  
  
 `_creat` применяет текущую маску доступа к файлу на `pmode` прежде чем устанавливать разрешения \(см. [\_umask](../../c-runtime-library/reference/umask.md)\).  `_creat` предоставлен в основном для обеспечения совместимости с предыдущими библиотеками.  Вызов `_open` с `_O_CREAT` и `_O_TRUNC` в параметре `oflag` эквивалентен `_creat` и предпочтителен для нового кода.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательный заголовок|  
|------------------|----------------------------|------------------------------|  
|`_creat`|\<io.h\>|\<sys\/types.h\>, \<sys\/stat.h\>, \<errno.h\>|  
|`_wcreat`|\<io.h\> или \<wchar.h\>|\<sys\/types.h\>, \<sys\/stat.h\>, \<errno.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
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
  
  **Created data file.**   
## См. также  
 [Низкоуровневый ввод\-вывод](../../c-runtime-library/low-level-i-o.md)   
 [\_chmod, \_wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [\_chsize](../../c-runtime-library/reference/chsize.md)   
 [\_close](../Topic/_close.md)   
 [\_dup, \_dup2](../../c-runtime-library/reference/dup-dup2.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_sopen, \_wsopen](../../c-runtime-library/reference/sopen-wsopen.md)   
 [\_umask](../../c-runtime-library/reference/umask.md)