---
title: "_execle, _wexecle | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _execle
- _wexecle
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
- wexecle
- _execle
- _wexecle
dev_langs:
- C++
helpviewer_keywords:
- wexecle function
- execle function
- _wexecle function
- _execle function
ms.assetid: 75efa9c5-96b7-4e23-acab-06258901f63a
caps.latest.revision: 22
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
ms.openlocfilehash: a9bda57c9520b46c3c28b492cf9a7f32637dffd8
ms.contentlocale: ru-ru
ms.lasthandoff: 04/01/2017

---
# <a name="execle-wexecle"></a>_execle, _wexecle
Загружает и выполняет новые дочерние процессы.  
  
> [!IMPORTANT]
>  Этот API не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]. Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
intptr_t _execle(   
   const char *cmdname,  
   const char *arg0,  
   ... const char *argn,  
   NULL,  
   const char *const *envp   
);  
intptr_t _wexecle(   
   const wchar_t *cmdname,  
   const wchar_t *arg0,  
   ... const wchar_t *argn,  
   NULL,  
   const char *const *envp   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `cmdname`  
 Путь к выполняемому файлу.  
  
 `arg0, ... argn`  
 Список указателей на параметры.  
  
 `envp`  
 Массив указателей на параметры среды.  
  
## <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения эти функции не возвращаются к вызывающему процессу. Возвращаемое значение-1 указывает на ошибку в этом случае `errno` значение глобальной переменной.  
  
|Значение `errno`|Описание|  
|-------------------|-----------------|  
|`E2BIG`|Пространство, требуемое для аргументов и параметров среды, превышает 32 КБ.|  
|`EACCES`|Указанный файл имеет нарушение блокировки или общего доступа.|  
|`EINVAL`|Недопустимый параметр.|  
|`EMFILE`|Слишком много открытых файлов. (Указанный файл необходимо открыть и определить, является ли он исполняемым.)|  
|`ENOENT`|Файл или путь не найден.|  
|`ENOEXEC`|Указанный файл не является исполняемым или имеет недопустимый формат исполняемого файла.|  
|`ENOMEM`|Недостаточно доступной памяти для выполнения нового процесса; либо доступная память повреждена, либо существует недопустимый блок, что указывает на неправильное выделение памяти для процесса, который выполняет вызов.|  
  
 Дополнительные сведения об этих кодах возврата см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Примечания  
 Каждая из этих функций загружает и выполняет новый процесс и передает каждый аргумент командной строки как отдельный параметр, а также передает массив указателей на параметры среды.  
  
 Эти функции `_execle` проверяют свои параметры. Если параметр `cmdname` или `arg0` является нулевым указателем или пустой строкой, эти функции вызывают обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если продолжение выполнения разрешено, эти функции устанавливают для `errno` значение `EINVAL` и возвращают -1. Ни один новый процесс не запущен.  
  
## <a name="requirements"></a>Требования  
  
|Функция|Обязательный заголовок|Необязательный заголовок|  
|--------------|---------------------|---------------------|  
|`_execle`|\<process.h>|\<errno.h>|  
|`_wexecle`|\<process.h> или \<wchar.h>|\<errno.h>|  
  
 Дополнительные сведения см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
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
