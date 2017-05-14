---
title: "_execl _wexecl | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _execl
- _wexecl
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-process-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _execl
- _wexecl
- wexecl
dev_langs:
- C++
helpviewer_keywords:
- _execl function
- wexecl function
- _wexecl function
- execl function
ms.assetid: 81fefb8a-0a06-4221-b2bc-be18e38e89f4
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 670d4ddaa4209830f842c68eb84d1840e1592790
ms.contentlocale: ru-ru
ms.lasthandoff: 04/01/2017

---
# <a name="execl-wexecl"></a>_execl, _wexecl
Загружает и выполняет новые дочерние процессы.  
  
> [!IMPORTANT]
>  Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
intptr_t _execl(   
   const char *cmdname,  
   const char *arg0,  
   ... const char *argn,  
   NULL   
);  
intptr_t _wexecl(  
   const wchar_t *cmdname,  
   const wchar_t *arg0,  
   ... const wchar_t *argn,  
   NULL   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `cmdname`  
 Путь к выполняемому файлу.  
  
 `arg0, ... argn`  
 Список указателей на параметры.  
  
## <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения эти функции не возвращаются к вызывающему процессу. Возвращаемое значение-1 указывает на ошибку в этом случае `errno` значение глобальной переменной.  
  
|Значение errno|Описание|  
|-----------------|-----------------|  
|`E2BIG`|Пространство, требуемое для аргументов и параметров среды, превышает 32 КБ.|  
|`EACCES`|Указанный файл имеет нарушение блокировки или общего доступа.|  
|`EINVAL`|Недопустимый параметр (один или несколько параметров представляли собой указатель null или пустую строку).|  
|`EMFILE`|Открыто слишком много файлов (указанный файл необходимо открыть и определить, является ли он исполняемым).|  
|`ENOENT`|Файл или путь не найден.|  
|`ENOEXEC`|Указанный файл не является исполняемым или имеет недопустимый формат исполняемого файла.|  
|`ENOMEM`|Недостаточно доступной памяти для выполнения нового процесса; либо доступная память повреждена, либо существует недопустимый блок, что указывает на неправильное выделение памяти для процесса, а значит вызывающий процесс был выделен ненадлежащим образом.|  
  
## <a name="remarks"></a>Примечания  
 Каждая из этих функций загружает и выполняет новый процесс, передавая все аргументы командной строки как отдельные параметры. Первым аргументом является имя команды или исполняемого файла, а второй должен быть таким же, как первый. В процессе запуска он становится `argv[0]`. Третий аргумент — это первый аргумент, `argv[1]`, выполняемого процесса.  
  
 Эти функции `_execl` проверяют свои параметры. Если параметр `cmdname` или `arg0` является нулевым указателем или пустой строкой, эти функции вызывают обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функцию задают для `errno` значение `EINVAL` и возвращают -1. Новые процессы не выполняются.  
  
## <a name="requirements"></a>Требования  
  
|Функция|Обязательный заголовок|Необязательный заголовок|  
|--------------|---------------------|---------------------|  
|`_execl`|\<process.h>|\<errno.h>|  
|`_wexecl`|\<process.h> или \<wchar.h>|\<errno.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Пример  
 См. пример в разделе [Функции _exec, _wexec](../../c-runtime-library/exec-wexec-functions.md).  
  
## <a name="see-also"></a>См. также  
 [Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)   
 [Функции _exec, _wexec](../../c-runtime-library/exec-wexec-functions.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [exit, _Exit, _exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [_onexit, _onexit_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [Функции _spawn, _wspawn](../../c-runtime-library/spawn-wspawn-functions.md)   
 [system, _wsystem](../../c-runtime-library/reference/system-wsystem.md)
