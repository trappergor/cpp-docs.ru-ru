---
title: "Пример программы, использующей обычный текст | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Тип _TCHAR"
  - "сопоставления, типы данных TCHAR.H"
  - "пример с обычным текстом [CRT]"
  - "Тип TCHAR"
  - "типы данных TCHAR.H, сопоставление"
ms.assetid: a03de0db-8118-4bd9-a03f-640e8dfc5ed3
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Пример программы, использующей обычный текст
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Майкрософт**  
  
 Следующая программа, GENTEXT.C, предоставляет более подробный пример использования универсальных текстовых сопоставлений, определенных в TCHAR.H:  
  
```  
// GENTEXT.C  
// use of generic-text mappings defined in TCHAR.H  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <string.h>  
#include <direct.h>  
#include <errno.h>  
#include <tchar.h>  
  
int __cdecl _tmain(int argc, _TCHAR **argv, _TCHAR **envp)  
{  
   _TCHAR buff[_MAX_PATH];  
   _TCHAR *str = _T("Astring");  
   char *amsg = "Reversed";  
   wchar_t *wmsg = L"Is";  
  
#ifdef _UNICODE  
   printf("Unicode version\n");  
#else /* _UNICODE */  
#ifdef _MBCS  
   printf("MBCS version\n");  
#else  
   printf("SBCS version\n");  
#endif  
#endif /* _UNICODE */  
  
   if (_tgetcwd(buff, _MAX_PATH) == NULL)  
       printf("Can't Get Current Directory - errno=%d\n", errno);  
   else  
       _tprintf(_T("Current Directory is '%s'\n"), buff);  
   _tprintf(_T("'%s' %hs %ls:\n"), str, amsg, wmsg);  
   _tprintf(_T("'%s'\n"), _tcsrev(_tcsdup(str)));  
   return 0;  
}  
  
```  
  
 Если `_MBCS` было определено, GENTEXT.C сопоставляется к следующей программе MBCS:  
  
```  
// crt_mbcsgtxt.c  
  
/*   
 * Use of generic-text mappings defined in TCHAR.H  
 * Generic-Text-Mapping example program  
 * MBCS version of GENTEXT.C  
 */  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <mbstring.h>  
#include <direct.h>  
  
int __cdecl main(int argc, char **argv, char **envp)  
{  
   char buff[_MAX_PATH];  
   char *str = "Astring";  
   char *amsg = "Reversed";  
   wchar_t *wmsg = L"Is";  
  
   printf("MBCS version\n");  
  
   if (_getcwd(buff, _MAX_PATH) == NULL) {  
       printf("Can't Get Current Directory - errno=%d\n", errno);  
   }  
   else {  
       printf("Current Directory is '%s'\n", buff);  
   }  
  
   printf("'%s' %hs %ls:\n", str, amsg, wmsg);  
   printf("'%s'\n", _mbsrev(_mbsdup((unsigned char*) str)));  
   return 0;  
}  
```  
  
 Если `_UNICODE` было определено, GENTEXT.C сопоставляется к следующей версии программы Unicode.  Дополнительные сведения об использовании `wmain` в программах Unicode в роли замены для `main` см. в разделе [Использование wmain](../c-language/using-wmain.md) в *Справочнике по языку C*.  
  
```  
// crt_unicgtxt.c  
  
/*   
 * Use of generic-text mappings defined in TCHAR.H  
 * Generic-Text-Mapping example program  
 * Unicode version of GENTEXT.C  
 */  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <string.h>  
#include <direct.h>  
  
int __cdecl wmain(int argc, wchar_t **argv, wchar_t **envp)  
{  
   wchar_t buff[_MAX_PATH];  
   wchar_t *str = L"Astring";  
   char *amsg = "Reversed";  
   wchar_t *wmsg = L"Is";  
  
   printf("Unicode version\n");  
  
   if (_wgetcwd(buff, _MAX_PATH) == NULL) {  
      printf("Can't Get Current Directory - errno=%d\n", errno);  
   }  
   else {  
       wprintf(L"Current Directory is '%s'\n", buff);  
   }  
  
   wprintf(L"'%s' %hs %ls:\n", str, amsg, wmsg);  
   wprintf(L"'%s'\n", wcsrev(wcsdup(str)));  
   return 0;  
}  
```  
  
 Если ни `_MBCS`, ни `_UNICODE` не были определены, GENTEXT.C сопоставляется в однобайтовый код ASCII следующим образом:  
  
```  
// crt_sbcsgtxt.c  
/*   
 * Use of generic-text mappings defined in TCHAR.H  
 * Generic-Text-Mapping example program  
 * Single-byte (SBCS) Ascii version of GENTEXT.C  
 */  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <string.h>  
#include <direct.h>  
  
int __cdecl main(int argc, char **argv, char **envp)  
{  
   char buff[_MAX_PATH];  
   char *str = "Astring";  
   char *amsg = "Reversed";  
   wchar_t *wmsg = L"Is";  
  
   printf("SBCS version\n");  
  
   if (_getcwd(buff, _MAX_PATH) == NULL) {  
       printf("Can't Get Current Directory - errno=%d\n", errno);  
   }  
   else {  
       printf("Current Directory is '%s'\n", buff);  
   }  
  
   printf("'%s' %hs %ls:\n", str, amsg, wmsg);  
   printf("'%s'\n", strrev(strdup(str)));  
   return 0;  
}  
```  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## См. также  
 [Универсальные текстовые сопоставления](../c-runtime-library/generic-text-mappings.md)   
 [Сопоставления типов данных](../c-runtime-library/data-type-mappings.md)   
 [Сопоставления констант и глобальных переменных](../c-runtime-library/constant-and-global-variable-mappings.md)   
 [Сопоставления процедур](../c-runtime-library/routine-mappings.md)   
 [Использование универсальных текстовых сопоставлений](../c-runtime-library/using-generic-text-mappings.md)