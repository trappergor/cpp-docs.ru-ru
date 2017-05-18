---
title: "Параметры ссылок | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- nothrownew.obj
- newmode.obj
- noenv.obj
- psetargv.obj
- loosefpmath.obj
- smallheap.obj
- fp10.obj
- nochkclr.obj
- chkstk.obj
- pcommode.obj
- pnoenv.obj
- link options [C++]
- invalidcontinue.obj
- pnothrownew.obj
- pwsetargv.obj
- pinvalidcontinue.obj
- wsetargv.obj
- binmode.obj
- setargv.obj
- noarg.obj
- pnewmode.obj
- commode.obj
- pthreadlocale.obj
- pbinmode.obj
- threadlocale.obj
- pnoarg.obj
ms.assetid: 05b5a77b-9dd1-494b-ae46-314598c770bb
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 3747170eb13e1b6fe5d489bc6cfdcf4c24195606
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="link-options"></a>Параметры ссылок
Каталог библиотек CRT содержит ряд небольших файлов объектов, которые обеспечивают работу определенных функций CRT без изменения кода. Они называются "параметрами ссылок", так как для их использования нужно только добавить эти параметры в командную строку постановщика.  
  
 Версии чистого режима существуют, но их не рекомендуется использовать в Visual Studio 2015. Для машинного кода и /clr используйте обычные версии, а для режима /clr:pure — чистые. Параметры компилятора **/CLR: pure** и **/CLR: safe** в Visual Studio 2015 не рекомендуется использовать.  
  
|Машинный код и /clr|Чистый режим|Описание|  
|----------------------|---------------|-----------------|  
|binmode.obj|pbinmode.obj|Устанавливает в качестве режима преобразования файлов по умолчанию двоичный режим. См. раздел [_fmode](../c-runtime-library/fmode.md).|  
|chkstk.obj|Н/Д|Обеспечивает поддержку проверки и распределения стека, если CRT не используется.|  
|commode.obj|pcommode.obj|Присваивает глобальному флагу фиксации значение "commit". См. раздел [fopen, _wfopen](../c-runtime-library/reference/fopen-wfopen.md) и [fopen_s, _wfopen_s](../c-runtime-library/reference/fopen-s-wfopen-s.md).|  
|fp10.obj|Н/Д|Изменяет управление точностью по умолчанию на 64 бита. См. раздел [Поддержка чисел с плавающей запятой](../c-runtime-library/floating-point-support.md).|  
|invalidcontinue.obj|pinvalidcontinue.obj|Определяет обработчик недопустимых параметров по умолчанию, который не делает ничего, т. е. недопустимые параметры, передаваемые в функции CRT, получают значение errno и возвращают ошибку.|  
|loosefpmath.obj|Н/Д|Гарантирует, что код с плавающей точкой кода допускает нестандартные значения.|  
|newmode.obj|pnewmode.obj|Заставляет [malloc](../c-runtime-library/reference/malloc.md) в случае ошибки вызывать новый обработчик. См. разделы [_set_new_mode](../c-runtime-library/reference/set-new-mode.md), [_set_new_handler](../c-runtime-library/reference/set-new-handler.md), [calloc](../c-runtime-library/reference/calloc.md) и [realloc](../c-runtime-library/reference/realloc.md).|  
|noarg.obj|pnoarg.obj|Отключает обработку аргументов argc и argv.|  
|nochkclr.obj|Н/Д|Ничего не делает. Удалите из проекта.|  
|noenv.obj|pnoenv.obj|Отключает создание кэшированной среды для CRT.|  
|nothrownew.obj|pnothrownew.obj|Позволяет использовать внеочередную версию новых функций в CRT. См. раздел [Операторы new и delete](../cpp/new-and-delete-operators.md).|  
|setargv.obj|psetargv.obj|Включает расширение аргументов заполнителей в командной строке. См. раздел [Расширение аргументов заполнителей](../c-language/expanding-wildcard-arguments.md).|  
|threadlocale.obj|pthreadlocale.obj|Включает языковой стандарт отдельного потока для всех новых потоков по умолчанию.|  
|wsetargv.obj|pwsetargv.obj|Включает расширение аргументов заполнителей в командной строке. См. раздел [Расширение аргументов заполнителей](../c-language/expanding-wildcard-arguments.md).|  
  
## <a name="see-also"></a>См. также  
 [Функции библиотеки CRT](../c-runtime-library/crt-library-features.md)
