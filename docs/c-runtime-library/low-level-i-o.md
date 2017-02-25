---
title: "Низкоуровневый ввод-вывод | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.io"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "файловые дескрипторы [C++]"
  - "файловые дескрипторы [C++], функции ввода и вывода"
  - "Ввод и вывод [CRT], функции"
  - "Ввод и вывод [CRT], низкоуровневый"
  - "процедуры низкоуровневого ввода и вывода"
ms.assetid: 53e11bdd-6720-481c-8b2b-3a3a569ed534
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Низкоуровневый ввод-вывод
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Эти функции вызывают непосредственно операционную систему для выполнения операций более низкого уровня, чем возможно с помощью потокового ввода\-вывода.  Низкоуровневые вызовы ввода и вывода данных не выполняют буферизацию или форматирование данных.  
  
 Низкоуровневые процедуры могут получить стандартные потоки, открытые при запуске программы, с помощью следующих предопределенных идентификаторов файлов.  
  
|Поток|Дескриптор файла|  
|-----------|----------------------|  
|`stdin`|0|  
|`stdout`|1|  
|`stderr`|2|  
  
 Низкоуровневые процедуры ввода\-вывода устанавливают глобальную переменную [errno](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md) при возникновении ошибки.  Необходимо включать STDIO.H при использовании низкоуровневых функций только если программа требует константы, определенные в STDIO.H, например, индикатор конца файла \(`EOF`\).  
  
### Низкоуровневые функции ввода\-вывода  
  
|Функция|Применение|  
|-------------|----------------|  
|[\_close](../Topic/_close.md)|Закрывает файл|  
|[\_commit](../c-runtime-library/reference/commit.md)|Записывает файл на диск|  
|[Функция \_creat, \_wcreat](../c-runtime-library/reference/creat-wcreat.md)|Создают файл|  
|[\_dup](../c-runtime-library/reference/dup-dup2.md)|Возвращает следующий доступный идентификатор файла для указанного файла|  
|[\_dup2](../c-runtime-library/reference/dup-dup2.md)|Создает второй идентификатор для указанного файла|  
|[\_eof](../c-runtime-library/reference/eof.md)|Проверка наличия конца файла.|  
|[\_lseek, \_lseeki64](../c-runtime-library/reference/lseek-lseeki64.md)|Перемещают указатель файла на заданное расположение|  
|[\_open, \_wopen](../c-runtime-library/reference/open-wopen.md)|Открывают файл|  
|[\_read](../Topic/_read.md)|Считывает данные из файла|  
|[\_sopen, \_wsopen](../c-runtime-library/reference/sopen-wsopen.md), [\_sopen\_s, \_wsopen\_s](../c-runtime-library/reference/sopen-s-wsopen-s.md)|Открывают файл для совместного использования|  
|[\_tell, \_telli64](../c-runtime-library/reference/tell-telli64.md)|Получают текущее положение файлового указателя|  
|[\_umask](../c-runtime-library/reference/umask.md), [\_umask\_s](../Topic/_umask_s.md)|Задают маску разрешений файлов|  
|[\_write](../c-runtime-library/reference/write.md)|Записывает данные в файл|  
  
 `_dup` и `_dup2` обычно используются для связывания предопределенных идентификаторов файлов с другими файлами.  
  
## См. также  
 [Ввод и вывод](../Topic/Input%20and%20Output.md)   
 [Процедуры среды выполнения по категориям](../c-runtime-library/run-time-routines-by-category.md)   
 [Системные вызовы](../Topic/System%20Calls.md)