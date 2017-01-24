---
title: "exit, _Exit, _exit | Microsoft Docs"
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
  - "_exit"
  - "exit"
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
  - "Exit"
  - "_exit"
  - "process/exit"
  - "process/_Exit"
  - "stdlib/exit"
  - "stdlib/_Exit"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "exit - функция"
  - "_exit - функция"
  - "процессы, завершающиеся"
  - "вызовы функций, завершающиеся"
  - "завершение процесса, вызов"
ms.assetid: b1501fa6-27c2-478c-9e93-cc4fd802a01f
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# exit, _Exit, _exit
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Завершает вызывающий процесс. Функция `exit` завершает его после очистки; `_exit` и `_Exit` завершают его мгновенно.  
  
> [!NOTE]
>  Не используйте этот метод для завершения приложения универсальной платформы Windows \(UWP\) или приложения [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)], за исключением сценариев тестирования или отладки. Программные способы закрытия приложения [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] и способы закрытия с помощью пользовательского интерфейса не разрешены. Дополнительные сведения о приложениях Windows 8 и 8.1 см. в статье [Жизненный цикл приложения](http://go.microsoft.com/fwlink/?LinkId=262853). Дополнительные сведения о приложениях Windows 10 см. в разделе [Практические руководства для приложений Windows 10](http://go.microsoft.com/fwlink/p/?linkid=619133).  
  
## Синтаксис  
  
```  
void exit(   
   int const status   
);  
void _Exit(   
   int const status   
);  
void _exit(   
   int const status   
);  
```  
  
#### Параметры  
 `status`  
 Код состояния завершения.  
  
## Заметки  
 Функции `exit`, `_Exit` и `_exit` завершают вызывающий процесс. Функция `exit` вызывает деструкторы для объектов локального потока, а затем вызывает в порядке "последним пришел — первым вышел" \(LIFO\) функции, зарегистрированные `atexit` и `_onexit`, а затем очищает все файловые буферы перед завершением процесса. Функции `_Exit` и `_exit` завершают процесс без удаления объектов локального потока или обработки функций `atexit` или `_onexit`, а также без очистки буферов потока.  
  
 Хотя вызовы `exit`, `_Exit` и `_exit` не возвращают значение, младший байт `status` становится доступным среде узла или ожидающему вызывающему процессу, если такой существует, после завершения процесса. Как правило, вызывающая функция задает для `status` значение 0 для указания нормального завершения или принимает другое значение для указания ошибки. Значение `status` становится доступным для пакетной команды операционной системы `ERRORLEVEL` и представлено одной из двух констант: `EXIT_SUCCESS`, которая представляет значение 0, или `EXIT_FAILURE`, которая представляет значение 1.  
  
 Функции `exit`, `_Exit`, `_exit`, `quick_exit`, `_cexit` и `_c_exit` ведут себя следующим образом.  
  
|Функция|Описание|  
|-------------|--------------|  
|`exit`|Выполняет полные процедуры завершения библиотеки C, завершает процесс и предоставляет полученный код состояния среде узла.|  
|`_Exit`|Выполняет минимальные процедуры завершения библиотеки C, завершает процесс и предоставляет полученный код состояния среде узла.|  
|`_exit`|Выполняет минимальные процедуры завершения библиотеки C, завершает процесс и предоставляет полученный код состояния среде узла.|  
|`quick_exit`|Выполняет быстрые процедуры завершения библиотеки C, завершает процесс и предоставляет полученный код состояния среде узла.|  
|`_cexit`|Выполняет полные процедуры завершения библиотеки C и возвращает управление вызывающему объекту. Не завершает процесс.|  
|`_c_exit`|Выполняет минимальные процедуры завершения библиотеки C и возвращает управление вызывающему объекту. Не завершает процесс.|  
  
 При вызове функции `exit`, `_Exit` или `_exit` деструкторы для любых существующих во время вызова временных или автоматических объектов не вызываются. Автоматический объект определяется в функции, в которой он не объявляется статическим. Временный объект — это объект, созданный компилятором. Чтобы удалить автоматический объект перед вызовом `exit`, `_Exit` или `_exit`, явным образом вызовите деструктор объекта следующим образом:  
  
```  
myObject.myClass::~myClass();  
```  
  
 Не используйте `DLL_PROCESS_ATTACH` для вызова `exit` из `DllMain`. Если требуется завершить функцию `DLLMain`, верните `FALSE` из `DLL_PROCESS_ATTACH`.  
  
## Требования  
  
|Функция|Обязательный заголовок|  
|-------------|----------------------------|  
|`exit`, `_Exit`, `_exit`|\< process.h \> или \< stdlib.h \>|  
  
 Дополнительные сведения о совместимости см. в статье [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```  
// crt_exit.c // This program returns an exit code of 1. The // error code could be tested in a batch file. #include <stdlib.h> int main( void ) { exit( 1 ); }  
```  
  
## Эквивалент в .NET Framework  
 [System::Diagnostics::Process::Kill](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.kill.aspx)  
  
## См. также  
 [Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [\_cexit, \_c\_exit](../../c-runtime-library/reference/cexit-c-exit.md)   
 [Функции \_exec, \_wexec](../../c-runtime-library/exec-wexec-functions.md)   
 [\_onexit, \_onexit\_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [quick\_exit](../../c-runtime-library/reference/quick-exit1.md)   
 [Функции \_spawn, \_wspawn](../Topic/_spawn,%20_wspawn%20Functions.md)   
 [system, \_wsystem](../../c-runtime-library/reference/system-wsystem.md)