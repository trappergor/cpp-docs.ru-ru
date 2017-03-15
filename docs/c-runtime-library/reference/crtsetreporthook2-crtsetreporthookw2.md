---
title: "_CrtSetReportHook2, _CrtSetReportHookW2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtSetReportHook2"
  - "_CrtSetReportHookW2"
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
apitype: "DLLExport"
f1_keywords: 
  - "CrtSetReportHookW2"
  - "CrtSetReportHook2"
  - "_CrtSetReportHookW2"
  - "_CrtSetReportHook2"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CrtSetReportHook2 - функция"
  - "_CrtSetReportHook2 - функция"
  - "_CrtSetReportHookW2 - функция"
  - "CrtSetReportHookW2 - функция"
ms.assetid: 12e5f68d-c8a7-4b1a-9a75-72ba4a8592d0
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# _CrtSetReportHook2, _CrtSetReportHookW2
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Устанавливает или удаляет определяемую клиентом функцию отчетов путём её прикрепления в процесс создания отчетов среды выполнения языка C \(только отладочная версия\).  
  
## Синтаксис  
  
```  
  
      int _CrtSetReportHook2(  
   int mode,  
   _CRT_REPORT_HOOK pfnNewHook  
);  
int _CrtSetReportHookW2(  
   int mode,  
   _CRT_REPORT_HOOKW pfnNewHook  
);  
```  
  
#### Параметры  
 `mode`  
 Предпринимаемое действие: `_CRT_RPTHOOK_INSTALL` или `_CRT_RPTHOOK_REMOVE`.  
  
 `pfnNewHook`  
 Уведомляет обработчик для установки или удаления версии функции для работы с узкими символами.  
  
 `pfnNewHook`  
 Уведомляет ловушку для установки или удаления в версии этой функции для расширенных символов.  
  
## Возвращаемое значение  
 \-1, если произошла ошибка, с установленными `EINVAL` или `ENOMEM`; в противном случае возвращает число ссылок `pfnNewHook` после вызова.  
  
## Заметки  
 `_CrtSetReportHook2` и `_CrtSetReportHookW2`  позволяют прикреплять или откреплять функцию, в то время как [\_CrtSetReportHook](../../c-runtime-library/reference/crtsetreporthook.md) позволяет только прикреплять функцию.  
  
 `_CrtSetReportHook2` или `_CrtSetReportHookW2`  следует использовать вместо `_CrtSetReportHook`, когда вызов ловушки сделан в DLL, и несколько DLL могут быть загружены и могут настраивать собственные функции\-ловушки.  В таком случае библиотеки DLL могут быть выгружены в другом порядке, чем они были загружены, а функция\-ловушка может продолжать указывать на выгруженную библиотеку DLL.  Любой отладочный вывод вызывает сбой процесса, если функции\-ловушки были добавлены с `_CrtSetReportHook`.  
  
 Все функции\-ловушки, добавленные с `_CrtSetReportHook`, вызываются при отсутствии функций\-ловушек, добавленные с `_CrtSetReportHook2` или `_CrtSetReportHookW2` , или если все функции\-ловушки, добавленные с `_CrtSetReportHook2` и `_CrtSetReportHookW2`  возвращают `FALSE`.  
  
 Доступна версия этой функции для расширенных символов.  Функции\-ловушки отчетов принимают строку, тип которой \(расширенные или узкие символы\) должен соответствовать версии используемой функции.  Используйте следующий прототип функции для ловушек отчетов, используемых с версией этой функции для расширенных символов.  
  
```  
int YourReportHook( int reportType, wchar_t *message, int *returnValue );  
```  
  
 Используйте следующий прототип для ловушек отчетов об узких символах:  
  
```  
int YourReportHook( int reportType, char *message, int *returnValue );  
```  
  
 Эти функции проверяют свои параметры.  Если `mode` или `pfnNewNook` недопустим, эти функции вызывают обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эти функции устанавливают для `errno` значение `EINVAL` и возвращают \-1.  
  
> [!NOTE]
>  Если приложение компилировано с `/clr` и функциональность отчетов вызывается после того, как приложение покидает main, среда CLR вызывает исключение, если функции отчета вызывают какие\-либо функции CRT.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательный заголовок|  
|------------------|----------------------------|------------------------------|  
|`_CrtSetReportHook2`|\<crtdbg.h\>|\<errno.h\>|  
|`_CrtSetReportHookW2`|\<crtdbg.h\>|\<errno.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Библиотеки  
 Только отладочные версии [Библиотеки времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## Пример  
  
```  
// crt_setreporthook2.c  
#include <windows.h>  
#include <stdio.h>  
#include <crtdbg.h>  
#include <assert.h>  
  
int __cdecl TestHook1(int nReportType, char* szMsg, int* pnRet)  
{  
   int nRet = FALSE;  
  
   printf("CRT report hook 1.\n");  
   printf("CRT report type is \"");  
   switch (nReportType)  
   {  
      case _CRT_ASSERT:  
      {  
         printf("_CRT_ASSERT");  
         // nRet = TRUE;   // Always stop for this type of report  
         break;  
      }  
  
      case _CRT_WARN:  
      {  
         printf("_CRT_WARN");  
         break;  
      }  
  
      case _CRT_ERROR:  
      {  
         printf("_CRT_ERROR");  
         break;  
      }  
  
      default:  
      {  
         printf("???Unknown???");  
         break;  
      }  
   }  
  
   printf("\".\nCRT report message is:\n\t");  
   printf(szMsg);  
  
   if   (pnRet)  
      *pnRet = 0;  
  
   return   nRet;  
}  
  
int __cdecl   TestHook2(int nReportType, char* szMsg, int* pnRet)  
{  
   int   nRet = FALSE;  
  
   printf("CRT report hook 2.\n");  
   printf("CRT report type is \"");  
   switch   (nReportType)  
   {  
      case _CRT_WARN:  
      {  
         printf("_CRT_WARN");  
         break;  
      }  
  
      case _CRT_ERROR:  
      {  
         printf("_CRT_ERROR");  
         break;  
      }  
  
      case _CRT_ASSERT:  
      {  
         printf("_CRT_ASSERT");  
         nRet = TRUE;   // Always stop for this type of report  
         break;  
      }  
  
      default:  
      {  
         printf("???Unknown???");  
         break;  
      }  
   }  
  
   printf("\".\nCRT report message is: \t");  
   printf(szMsg);  
  
   if   (pnRet)  
      *pnRet = 0;  
   // printf("CRT report code is %d.\n", *pnRet);  
   return   nRet;  
}  
  
int   main(int argc, char* argv[])  
{  
   int   nRet = 0;  
  
   nRet = _CrtSetReportHook2(_CRT_RPTHOOK_INSTALL, TestHook1);  
   printf("_CrtSetReportHook2(_CRT_RPTHOOK_INSTALL, TestHook1)"  
          " returned %d\n", nRet);  
   nRet = _CrtSetReportHook2(_CRT_RPTHOOK_INSTALL, TestHook2);  
   printf("_CrtSetReportHook2(_CRT_RPTHOOK_INSTALL, TestHook2)"  
          " returned %d\n", nRet);  
   nRet = _CrtSetReportHook2(_CRT_RPTHOOK_INSTALL, TestHook2);  
   printf("_CrtSetReportHook2(_CRT_RPTHOOK_INSTALL, TestHook2)"  
          " returned %d\n", nRet);  
   nRet = _CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook1);  
   printf("_CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook1)"  
          " returned %d\n", nRet);  
   nRet = _CrtSetReportHook2(_CRT_RPTHOOK_INSTALL, TestHook1);  
   printf("_CrtSetReportHook2(_CRT_RPTHOOK_INSTALL, TestHook1)"  
          " returned %d\n", nRet);  
  
   _ASSERT(0);  
  
   nRet = _CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook2);  
   printf("_CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook2)"  
          " returned %d\n", nRet);  
   nRet = _CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook2);  
   printf("_CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook2)"  
          " returned %d\n", nRet);  
   nRet = _CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook2);  
   printf("_CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook2)"  
          " returned %d\n", nRet);  
   nRet = _CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook1);  
   printf("_CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook1)"  
          " returned %d\n", nRet);  
  
   return   nRet;  
}  
```  
  
## Output  
  
```  
_CrtSetReportHook2(_CRT_RPTHOOK_INSTALL, TestHook1) returned 0  
_CrtSetReportHook2(_CRT_RPTHOOK_INSTALL, TestHook2) returned 0  
_CrtSetReportHook2(_CRT_RPTHOOK_INSTALL, TestHook2) returned 0  
_CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook1) returned 0  
_CrtSetReportHook2(_CRT_RPTHOOK_INSTALL, TestHook1) returned 0  
_CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook2) returned 0  
_CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook2) returned 0  
_CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook2) returned 0  
_CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook1) returned 0  
```  
  
## См. также  
 [Процедуры отладки](../../c-runtime-library/debug-routines.md)