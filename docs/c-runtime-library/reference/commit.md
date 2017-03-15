---
title: "_commit | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_commit"
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
  - "_commit"
  - "commit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_commit - функция"
  - "commit - функция"
  - "сохранение файлов на диск"
  - "файлы [C++], очистка"
  - "очистка файлов на диск"
ms.assetid: d0c74d3a-4f2d-4fb0-b140-2d687db3d233
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# _commit
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Записывает файл непосредственно на диск.  
  
## Синтаксис  
  
```  
int _commit(   
   int fd   
);  
```  
  
#### Параметры  
 `fd`  
 Идентификатор файла, ссылающийся на открытый файл.  
  
## Возвращаемое значение  
 `_commit` возвращает 0, если файл был успешно сброшен на диск.  Возвращаемое значение –1 указывает на ошибку.  
  
## Заметки  
 Функция `_commit` заставляет операционную систему записать файл, связанный с `fd`, на диск.  Этот метод гарантирует, что указанный файл сбрасывается немедленно, а не по усмотрению операционной системы.  
  
 Если параметр `fd` является недопустимым дескриптором файла, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если выполнение может продолжиться, функция возвращает \-1 и устанавливает `errno` в `EBADF`  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательные заголовки|  
|------------------|----------------------------|------------------------------|  
|`_commit`|\<io.h\>|\<errno.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## См. также  
 [Низкоуровневый ввод\-вывод](../../c-runtime-library/low-level-i-o.md)   
 [Функция \_creat, \_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_read](../Topic/_read.md)   
 [\_write](../../c-runtime-library/reference/write.md)