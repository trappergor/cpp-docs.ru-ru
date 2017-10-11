---
title: "_pgmptr, _wpgmptr | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- pgmptr
- _pgmptr
- wpgmptr
- _wpgmptr
dev_langs:
- C++
helpviewer_keywords:
- wpgmptr function
- _wpgmptr function
- _pgmptr function
- pgmptr function
ms.assetid: 4d44b515-0eff-4136-8bc4-684195f218f5
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 21d3ad8d4cbd73c2a1ab99497db2f671196de523
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="pgmptr-wpgmptr"></a>_pgmptr, _wpgmptr
Путь к исполняемому файлу. Нерекомендуемый. Используйте [_get_pgmptr](../c-runtime-library/reference/get-pgmptr.md) и [_get_wpgmptr](../c-runtime-library/reference/get-wpgmptr.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
extern char *_pgmptr;  
extern wchar_t *_wpgmptr;  
```  
  
## <a name="remarks"></a>Примечания  
 Когда программа выполняется из интерпретатора команд (Cmd.exe), `_pgmptr` автоматически инициализируется полным путем к исполняемому файлу. Например, если Hello.exe находится в C:\BIN и C:\BIN содержится в пути, для переменной `_pgmptr` устанавливается значение "C:\BIN\Hello.exe" при выполнении команды:  
  
```  
C> hello   
```  
  
 Когда программа выполняется не из командной строки, переменная `_pgmptr` может быть инициализирована именем программы (базовое имя файла без расширения) либо именем файла, относительным путем или полным путем.  
  
 Переменная `_wpgmptr` представляет собой эквивалент переменной `_pgmptr` для работы с программами, которые используют `wmain`.  
  
### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tpgmptr`|`_pgmptr`|`_pgmptr`|`_wpgmptr`|  
  
## <a name="requirements"></a>Требования  
  
|Переменная|Обязательный заголовок|  
|--------------|---------------------|  
|`_pgmptr`, `_wpgmptr`|\<stdlib.h>|  
  
## <a name="example"></a>Пример  
 В следующей программе показано использование переменной `_pgmptr`.  
  
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
  
 Можно использовать переменную `_wpgmptr`, изменив `%Fs` на `%S` и `main` на `wmain`.  
  
## <a name="see-also"></a>См. также  
 [Глобальные переменные](../c-runtime-library/global-variables.md)
