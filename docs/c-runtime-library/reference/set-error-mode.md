---
title: "_set_error_mode | Microsoft Docs"
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
  - "_set_error_mode"
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
  - "set_error_mode"
  - "_set_error_mode"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_set_error_mode - функция"
  - "set_error_mode - функция"
ms.assetid: f0807be5-73d1-4a32-a701-3c9bdd139c5c
caps.latest.revision: 21
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _set_error_mode
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Изменяет `__error_mode` для определения отличного от используемого по умолчанию местоположения, куда среда выполнения C записывает сообщение об ошибке для ошибок, которые могут вызвать завершение программы.  
  
> [!IMPORTANT]
>  Этот API не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  Дополнительные сведения см. в разделе [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
```  
int _set_error_mode(  
   int modeval   
);  
```  
  
#### Параметры  
 `modeval`  
 Назначение сообщений об ошибках.  
  
## Возвращаемое значение  
 Возвращает старое значение или \-1, если возникла ошибка.  
  
## Заметки  
 Управляет приемником потока ошибок, устанавливая значение `__error_mode`.  Например, можно направить вывод в стандартную ошибку или использовать API `MessageBox`.  
  
 Параметру `modeval` может быть присвоено одно из следующих значений:  
  
|Параметр|Описание|  
|--------------|--------------|  
|`_OUT_TO_DEFAULT`|Приемник ошибок определяется значением `__app_type`.|  
|`_OUT_TO_STDERR`|Приемником ошибок является стандартная ошибка.|  
|`_OUT_TO_MSGBOX`|Приемником ошибок является окно сообщения.|  
|`_REPORT_ERRMODE`|Сообщает текущее значение `__error_mode`.|  
  
 При передаче функции значения, отличного от перечисленных, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если выполнение может быть продолжено, `_set_error_mode` задает для `errno` значение `EINVAL` и возвращает значение \-1.  
  
 При использовании с [assert](../../c-runtime-library/reference/assert-macro-assert-wassert.md) `_set_error_mode` отображает ставший причиной сбоя оператор в диалоговом окне и предоставляет возможность нажать кнопку `Ignore` для продолжения выполнения программы.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_set_error_mode`|\<stdlib.h\>|  
  
## Пример  
  
```  
// crt_set_error_mode.c  
// compile with: /c  
#include <stdlib.h>  
#include <assert.h>  
  
int main()  
{  
   _set_error_mode(_OUT_TO_STDERR);  
   assert(2+2==5);  
}  
```  
  
  **Assertion failed: 2\+2\=\=5, file crt\_set\_error\_mode.c, line 8**  
**Это приложение запросило завершение среды выполнения необычным способом.  За дополнительной информацией обращайтесь в службу поддержки приложения.**    
## См. также  
 [Макрос assert, \_assert, \_wassert](../../c-runtime-library/reference/assert-macro-assert-wassert.md)