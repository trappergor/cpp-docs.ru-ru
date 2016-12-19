---
title: "system, _wsystem | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "system"
  - "_wsystem"
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
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_tsystem"
  - "_wsystem"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_tsystem - функция"
  - "_wsystem - функция"
  - "средство интерпретации команд"
  - "команды, выполнение"
  - "системная функция"
  - "tsystem - функция"
  - "wsystem - функция"
ms.assetid: 7d3df2b6-f742-49ce-bf52-012b0aee3df5
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# system, _wsystem
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Выполняет команду.  
  
> [!IMPORTANT]
>  Этот API не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  Дополнительные сведения см. в разделе [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
```  
int system(  
   const char *command   
);  
int _wsystem(  
   const wchar_t *command   
);  
```  
  
#### Параметры  
 `command`  
 Команда для выполнения.  
  
## Возвращаемое значение  
 Если параметр `command` имеет значение `NULL` и найден интерпретатор команд, возвращает ненулевое значение.  Если интерпретатор команд не найден, возвращает значение 0 и задает для параметра `errno` значение `ENOENT`.  Если параметр `command` не равен `NULL`, то функция `system` возвращает значение, возвращаемое интерпретатором команд.  Она возвращает значение 0, только если интерпретатор команд возвращает значение 0.  Возвращаемое значение "–1" указывает на ошибку, и для параметра `errno` устанавливается в одно из следующих значений:  
  
 `E2BIG`  
 Список аргументов \(который зависит от системы\) слишком велик.  
  
 `ENOENT`  
 Интерпретатор команд не найден.  
  
 `ENOEXEC`  
 Файл интерпретатора команд не может быть выполнен из\-за недопустимого формата.  
  
 `ENOMEM`  
 Недостаточно доступной памяти для выполнения команды; или доступная память повреждена; или существует недопустимый блок, что указывает на неправильное выделение памяти для процесса, который выполняет вызов.  
  
 Дополнительные сведения об этих кодах возврата см. в разделе [\_doserrno, errno, \_sys\_errlist и \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
## Заметки  
 Функция `system` передает параметр `command` интерпретатору команд, который выполняет эту строку как команду операционной системы.  Для поиска файла интерпретатора команд CMD.exe функция `system` использует переменные среды `COMSPEC` и `PATH`.  Если параметр `command` имеет значение `NULL`, функция только проверяет, существует ли интерпретатор команд.  
  
 Перед вызовом функции `fflush` необходимо явно очистить \(с помощью функции `_flushall` или `system`\) или закрыть все потоки.  
  
 `_wsystem` — это версия `system` с расширенными символами; аргумент `command` для `_wsystem` — строка расширенных символов.  В остальном эти функции ведут себя одинаково.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tsystem`|`system`|`system`|`_wsystem`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`system`|\< process.h \> или \< stdlib.h \>|  
|`_wsystem`|\<process.h\>, \<stdlib.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
 В этом примере функция `system` используется для печати \(TYPE\) текстового файла.  
  
```  
// crt_system.c  
  
#include <process.h>  
  
int main( void )  
{  
   system( "type crt_system.txt" );  
}  
```  
  
## Входные данные: crt\_system.txt  
  
```  
Line one.  
Line two.  
```  
  
### Вывод  
  
```  
Line one.  
Line two.  
```  
  
## Эквивалент в .NET Framework  
  
-   [Класс System::Diagnostics::ProcessStartInfo](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)  
  
-   [Класс System::Diagnostics::Process](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)  
  
## См. также  
 [Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)   
 [Функции \_exec, \_wexec](../../c-runtime-library/exec-wexec-functions.md)   
 [exit, \_Exit, \_exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [\_flushall](../../c-runtime-library/reference/flushall.md)   
 [Функции \_spawn, \_wspawn](../Topic/_spawn,%20_wspawn%20Functions.md)