---
title: "_umask | Microsoft Docs"
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
  - "_umask"
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
  - "api-ms-win-crt-filesystem-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_umask"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_umask - функция"
  - "разрешения файла [C++]"
  - "файлы [C++], параметры разрешений для"
  - "маски"
  - "маски, параметры разрешений файлов"
  - "umask - функция"
ms.assetid: 5e9a13ba-5321-4536-8721-6afb6f4c8483
caps.latest.revision: 21
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _umask
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Задает маску разрешений для файлов по умолчанию.  Существует более безопасная версия этой функций; см. раздел [\_umask\_s](../Topic/_umask_s.md).  
  
## Синтаксис  
  
```  
int _umask(  
   int pmode   
);  
```  
  
#### Параметры  
 `pmode`  
 Параметр разрешений по умолчанию.  
  
## Возвращаемое значение  
 `_umask` возвращает предыдущее значение `pmode`.  Нет какого\-либо возврата ошибки.  
  
## Заметки  
 Функция `_umask` задает маску разрешений для файлов текущего процесса в режим, указанный в `pmode`*.* Маска разрешений для файлов изменяет настройки разрешений новых файлов, созданных функциями `_creat`, `_open` или `_sopen`.  Если бит в маске равен 1, соответствующий бит в запрошенном значении разрешения для файла устанавливается в 0 \(запрещено\).  Если бит в маске равен 0, соответствующий бит остается без изменений.  Настройка разрешений для нового файла не устанавливается до тех пор, пока файл не закрыт в первый раз.  
  
 Целочисленное выражение `pmode` содержит одну или обе следующих константы манифеста, определенных в SYS\\STAT.H:  
  
 `_S_IWRITE`  
 Запись разрешена.  
  
 `_S_IREAD`  
 Чтение разрешено.  
  
 `_S_IREAD | _S_IWRITE`  
 Чтение и запись разрешены.  
  
 Если предоставлены обе константы, они объединяются битовым оператором OR \(          `|`  \).  Если аргумент `pmode` равен `_S_IREAD`, чтение не разрешено \(файл доступен только для записи\).  Если аргумент `pmode` равен `_S_IWRITE`, запись не разрешена \(файл доступен только для чтения\).  Например, если бит записи устанавливается в маске, то все новые файлы будут доступны только для чтения.  Обратите внимание, что для операционных систем MS\-DOS и Windows, все файлы доступны для чтения; невозможно предоставить им доступ только на запись.  Поэтому установка бита чтения в `_umask` не влияет на режимы файла.  
  
 Если `pmode` \- не сочетание одной из констант манифеста, или он содержит другой набор констант, функция просто игнорирует их.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_umask`|\<io.h\>, \<sys\/stat.h\>, \<sys\/types.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Библиотеки  
 Все версии [библиотек времени выполнения C](../../c-runtime-library/crt-library-features.md).  
  
## Пример  
  
```  
// crt_umask.c  
// compile with: /W3  
// This program uses _umask to set  
// the file-permission mask so that all future  
// files will be created as read-only files.  
// It also displays the old mask.  
#include <sys/stat.h>  
#include <sys/types.h>  
#include <io.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int oldmask;  
  
   /* Create read-only files: */  
   oldmask = _umask( _S_IWRITE ); // C4996  
   // Note: _umask is deprecated; consider using _umask_s instead  
   printf( "Oldmask = 0x%.4x\n", oldmask );  
}  
```  
  
  **Oldmask \= 0x0000**   
## Эквивалент в .NET Framework  
 [System::IO::File::SetAttributes](https://msdn.microsoft.com/en-us/library/system.io.file.setattributes.aspx)  
  
## См. также  
 [Обработка файлов](../../c-runtime-library/file-handling.md)   
 [Низкоуровневый ввод\-вывод](../../c-runtime-library/low-level-i-o.md)   
 [\_chmod, \_wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [Функция \_creat, \_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [\_mkdir, \_wmkdir](../Topic/_mkdir,%20_wmkdir.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)