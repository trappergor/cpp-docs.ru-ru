---
title: "_pgmptr, _wpgmptr | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "pgmptr"
  - "_pgmptr"
  - "wpgmptr"
  - "_wpgmptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_pgmptr - функция"
  - "_wpgmptr - функция"
  - "pgmptr - функция"
  - "wpgmptr - функция"
ms.assetid: 4d44b515-0eff-4136-8bc4-684195f218f5
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# _pgmptr, _wpgmptr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Путь к исполняемому файлу.  Не рекомендуется; используйте [\_get\_pgmptr](../c-runtime-library/reference/get-pgmptr.md) и [\_get\_wpgmptr](../c-runtime-library/reference/get-wpgmptr.md).  
  
## Синтаксис  
  
```  
extern char *_pgmptr;  
extern wchar_t *_wpgmptr;  
```  
  
## Заметки  
 Когда программа выполняется из интерпретатора команд \(Cmd.exe\), `_pgmptr` автоматически инициализируется полным путем к исполняемому файлу.  Например, если Hello.exe находится в C:\\BIN и C:\\BIN содержится в пути, `_pgmptr` установлено на C: \\BIN\\Hello.exe при выполнении:  
  
```  
C> hello   
```  
  
 Когда программа не выполняется из командной строки, `_pgmptr` может быть инициализирован названием программы \(базовое имя файла без расширения\) или именем файла, относительным путем или полным путем.  
  
 `_wpgmptr` работающий с расширенными символами эквивалент `_pgmptr` для работы с программами, которые используют `wmain`.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tpgmptr`|`_pgmptr`|`_pgmptr`|`_wpgmptr`|  
  
## Требования  
  
|Переменная|Обязательный заголовок|  
|----------------|----------------------------|  
|`_pgmptr`, `_wpgmptr`|\<stdlib.h\>|  
  
## Пример  
 В следующей программе показано использование функции `_pgmptr`.  
  
```  
// crt_pgmptr.c  
// compile with: /W3  
// The following program demonstrates the use of _pgmptr.  
//  
#include <stdio.h>  
#include <stdlib.h>  
int main( void )  
{  
   printf("The full path of the executing program is : %Fs\n",   
     _pgmptr); // C4996  
   // Note: _pgmptr is deprecated; use _get_pgmptr instead  
}  
```  
  
 Можно использовать `_wpgmptr` путем изменения `%Fs` на `%S` и `main` на `wmain`.  
  
## См. также  
 [Глобальные переменные](../c-runtime-library/global-variables.md)