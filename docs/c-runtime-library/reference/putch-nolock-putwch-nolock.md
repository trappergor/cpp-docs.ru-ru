---
title: "_putch_nolock, _putwch_nolock | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_putwch_nolock"
  - "_putch_nolock"
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
  - "api-ms-win-crt-conio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_putch_nolock"
  - "_puttch_nolock"
  - "putch_nolock"
  - "putwch_nolock"
  - "_putwch_nolock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_putch_nolock - функция"
  - "_puttch_nolock - функция"
  - "_putwch_nolock - функция"
  - "знаки, написание"
  - "консоль, запись знаков в"
  - "putch_nolock - функция"
  - "puttch_nolock - функция"
  - "putwch_nolock - функция"
ms.assetid: edbc811d-bac6-47fa-a872-fe4f3a1590b0
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# _putch_nolock, _putwch_nolock
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Записывает символ на консоль без блокирования потока.  
  
> [!IMPORTANT]
>  Этот API невозможно использовать в приложениях, запускаемых в среде выполнения Windows.  Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
```  
  
      int _putch_nolock(  
int c   
);  
wint_t _putwch_nolock(  
wchar_t c  
);  
```  
  
#### Параметры  
 *c*  
 Символ, который требуется вывести.  
  
## Возвращаемое значение  
 Возвращает значение *c* в случае успеха.  Если **\_putch\_nolock** завершается ошибкой, возвращается значение **EOF**; если **\_putwch\_nolock** завершается ошибкой, возвращается значение **WEOF**.  
  
## Заметки  
 **\_putch\_nolock** и **\_putwch\_nolock** совпадают с **\_putch** и **\_putwch** соответственно, за исключением того, что они не защищены от взаимодействия с другими потоками.  Они могут выполняться быстрее, поскольку не создают дополнительную нагрузку, связанную с блокировкой работы других потоков.  Используйте эти функции только в потокобезопасных контекстах, например в однопоточных приложениях или если вызываемая область уже обрабатывает изоляцию потоков.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|**\_puttch\_nolock**|**\_putch\_nolock**|**\_putch\_nolock**|**\_putwch\_nolock**|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|**\_putch\_nolock**|\<conio.h\>|  
|**\_putwch\_nolock**|\<conio.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Библиотеки  
 Все версии [библиотек времени выполнения C](../../c-runtime-library/crt-library-features.md).  
  
## См. также  
 [Ввод\-вывод на консоль и порт](../../c-runtime-library/console-and-port-i-o.md)   
 [\_cprintf, \_cprintf\_l, \_cwprintf, \_cwprintf\_l](../../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)   
 [\_getch, \_getwch](../Topic/_getch,%20_getwch.md)