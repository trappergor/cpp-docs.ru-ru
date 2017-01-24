---
title: "_rmdir, _wrmdir | Microsoft Docs"
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
  - "_wrmdir"
  - "_rmdir"
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
  - "trmdir"
  - "_trmdir"
  - "wrmdir"
  - "_rmdir"
  - "_wrmdir"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_rmdir - функция"
  - "_trmdir - функция"
  - "_wrmdir - функция"
  - "каталоги [C++], удаление"
  - "каталоги [C++], удаление"
  - "rmdir - функция"
  - "trmdir - функция"
  - "wrmdir - функция"
ms.assetid: 652c2a5a-b0ac-4493-864e-1edf484333c5
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _rmdir, _wrmdir
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Удаляет каталог.  
  
## Синтаксис  
  
```  
  
      int _rmdir(  
   const char *dirname   
);  
int _wrmdir(  
   const wchar_t *dirname   
);  
```  
  
#### Параметры  
 `dirname`  
 Путь к каталогу, который необходимо удалить.  
  
## Возвращаемое значение  
 Каждая из этих функций возвращает 0, если каталог успешно удален.  Возвращаемое значение, равное \-1, указывает на ошибку, и `errno` устанавливается в одно из следующих значений:  
  
 **ENOTEMPTY**  
 Указанный путь \- не каталог, каталог не пуст, или каталог является либо текущей рабочей папкой, либо корневым каталогом.  
  
 `ENOENT`  
 Недопустимый путь.  
  
 **EACCES**  
 В программе есть открытый дескриптор каталога.  
  
 Дополнительные сведения об этих и других кодах возврата см. в разделе [\_doserrno, errno, \_sys\_errlist и \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
## Заметки  
 Функция `_rmdir` удаляет каталог, указанный в `dirname`.  Каталог должен быть пустым и не должен быть текущей рабочей папкой или корневым каталогом.  
  
 `_wrmdir` — двухбайтовая версия `_rmdir`; аргумент `dirname` для `_wrmdir` \- строка двухбайтовых знаков.  В остальных случаях поведение `_wrmdir` и `_rmdir` идентично.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_trmdir`|`_rmdir`|`_rmdir`|`_wrmdir`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_rmdir`|\<direct.h\>|  
|`_wrmdir`|\<direct.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Библиотеки  
 Все версии [библиотек времени выполнения C](../../c-runtime-library/crt-library-features.md).  
  
## Пример  
 См. пример для [\_mkdir](../Topic/_mkdir,%20_wmkdir.md).  
  
## Эквивалент в .NET Framework  
 [System::IO::Directory::Delete](https://msdn.microsoft.com/en-us/library/system.io.directory.delete.aspx)  
  
## См. также  
 [Управление каталогами](../../c-runtime-library/directory-control.md)   
 [\_chdir, \_wchdir](../Topic/_chdir,%20_wchdir.md)   
 [\_mkdir, \_wmkdir](../Topic/_mkdir,%20_wmkdir.md)