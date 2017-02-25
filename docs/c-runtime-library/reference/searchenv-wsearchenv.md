---
title: "_searchenv, _wsearchenv | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_searchenv"
  - "_wsearchenv"
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
  - "api-ms-win-crt-environment-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_wsearchenv"
  - "_tsearchenv"
  - "wsearchenv"
  - "_searchenv"
  - "searchenv"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_searchenv - функция"
  - "_tsearchenv - функция"
  - "_wsearchenv - функция"
  - "пути в среде"
  - "пути в среде, поиск файлов"
  - "файлы [C++], поиск"
  - "searchenv - функция"
  - "tsearchenv - функция"
  - "wsearchenv - функция"
ms.assetid: 9c944a27-d326-409b-aee6-410e8762d9d3
caps.latest.revision: 33
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 33
---
# _searchenv, _wsearchenv
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Использует пути в среде для поиска файла.  Существуют более безопасные версии этих функций; см. раздел [\_searchenv\_s, \_wsearchenv\_s](../Topic/_searchenv_s,%20_wsearchenv_s.md).  
  
> [!IMPORTANT]
>  Этот API не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  Дополнительные сведения см. в разделе [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
```  
void _searchenv(  
   const char *filename,  
   const char *varname,  
   char *pathname   
);  
void _wsearchenv(  
   const wchar_t *filename,  
   const wchar_t *varname,  
   wchar_t *pathname   
);  
template <size_t size>  
void _searchenv(  
   const char *filename,  
   const char *varname,  
   char (&pathname)[size]  
); // C++ only  
template <size_t size>  
void _wsearchenv(  
   const wchar_t *filename,  
   const wchar_t *varname,  
   wchar_t (&pathname)[size]  
); // C++ only  
```  
  
#### Параметры  
 `filename`  
 Имя искомого файла.  
  
 `varname`  
 Искомая среда.  
  
 `pathname`  
 Буфер для хранения полного пути.  
  
## Заметки  
 Процедура `_searchenv` ищет целевой файл в указанном домене.  Переменной `varname` может быть любая переменная среды или переменная, определяемая пользователем, например `PATH`, `LIB` или `INCLUDE`, и определяющая список путей к каталогам.  Поскольку процедура `_searchenv` чувствительна к регистру, значение параметра `varname` должно соответствовать регистру переменной среды.  
  
 Сначала процедура выполняет поиск файла в текущем рабочем каталоге.  Если файл не найден, он ищет его в каталогах, указанных в переменной среды.  Если целевой файл содержится в одном из этих каталогов, созданный путь копируется в `pathname`.  Если файл `filename` не найден, `pathname` содержит пустую строку с завершающим нулем.  
  
 Буфер `pathname` должен содержать не меньше `_MAX_PATH` знаков, чтобы вместить полное имя созданного пути.  В противном случае `_searchenv` может вызвать переполнение буфера `pathname` и привести к непредвиденному поведению.  
  
 `_wsearchenv` — это двухбайтовая версия `_searchenv`, а аргументы для `_wsearchenv` представляют собой двухбайтовые строки.  Поведение `_wsearchenv` и `_searchenv` идентично в противном случае.  
  
 Если `filename` является пустой строкой, эти функции возвращают `ENOENT`.  
  
 Если `filename` или `pathname` является указателем `NULL`, вызывается обработчик недопустимых параметров, как описано в статье [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если разрешается продолжать выполнение, эти функции возвращают \-1 и задают `errno` значение `EINVAL`.  
  
 Дополнительные сведения о `errno` и кодах ошибок см. в разделе [Константы errno](../../c-runtime-library/errno-constants.md).  
  
 В C\+\+ эти функции имеют шаблонные перегрузки, которые вызывают более новые и безопасные аналоги этих функций.  Дополнительные сведения см. в статье [Безопасные перегрузки шаблонов](../Topic/Secure%20Template%20Overloads.md).  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tsearchenv`|`_searchenv`|`_searchenv`|`_wsearchenv`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_searchenv`|\<stdlib.h\>|  
|`_wsearchenv`|\<stdlib.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```  
// crt_searchenv.c  
// compile with: /W3  
// This program searches for a file in  
// a directory that's specified by an environment variable.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char pathbuffer[_MAX_PATH];  
   char searchfile[] = "CL.EXE";  
   char envvar[] = "PATH";  
  
   // Search for file in PATH environment variable:  
   _searchenv( searchfile, envvar, pathbuffer ); // C4996  
   // Note: _searchenv is deprecated; consider using _searchenv_s  
   if( *pathbuffer != '\0' )  
      printf( "Path for %s:\n%s\n", searchfile, pathbuffer );  
   else  
      printf( "%s not found\n", searchfile );  
}  
```  
  
  **Путь для файла CL. EXE:**  
**C:\\Program Files\\Microsoft Visual Studio 8\\VC\\BIN\\CL.EXE**   
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Управление каталогами](../../c-runtime-library/directory-control.md)   
 [getenv, \_wgetenv](../../c-runtime-library/reference/getenv-wgetenv.md)   
 [\_putenv, \_wputenv](../../c-runtime-library/reference/putenv-wputenv.md)   
 [\_searchenv\_s, \_wsearchenv\_s](../Topic/_searchenv_s,%20_wsearchenv_s.md)