---
title: "_spawnl, _wspawnl | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wspawnl
- _spawnl
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
- spawnl
- wspawnl
- _wspawnl
- _spawnl
dev_langs:
- C++
helpviewer_keywords:
- spawnl function
- processes, creating
- _spawnl function
- processes, executing new
- _wspawnl function
- wspawnl function
- process creation
ms.assetid: dd4584c9-7173-4fc5-b93a-6e7d3c2316d7
caps.latest.revision: 17
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
ms.openlocfilehash: 91000dba7d7fe1ff505eee30d60bc60936ef4971
ms.contentlocale: ru-ru
ms.lasthandoff: 04/01/2017

---
# <a name="spawnl-wspawnl"></a>_spawnl, _wspawnl
Создает и выполняет новый процесс.  
  
> [!IMPORTANT]
>  Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
intptr_t _spawnl(  
   int mode,  
   const char *cmdname,  
   const char *arg0,  
   const char *arg1,  
   ... const char *argn,  
   NULL   
);  
intptr_t _wspawnl(  
   int mode,  
   const wchar_t *cmdname,  
   const wchar_t *arg0,  
   const wchar_t *arg1,  
   ... const wchar_t *argn,  
   NULL   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `mode`  
 Режим выполнения для вызывающего процесса.  
  
 `cmdname`  
 Путь к выполняемому файлу.  
  
 `arg0, arg1, ... argn`  
 Список указателей на аргументы. Аргумент `arg0` обычно является указателем на параметр `cmdname`. Аргументы `arg1` – `argn` являются указателями на строки символов, которые образуют новый список аргументов. После `argn`должно следовать указатель `NULL` , отмечающий конец списка аргументов.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращаемое значение синхронных функций `_spawnl` или `_wspawnl` (для параметра `_P_WAIT` указано значение `mode`) — это состояние завершения нового процесса. Возвращаемое значение асинхронной функции `_spawnl` или `_wspawnl` (для параметра`_P_NOWAIT` указано значение `_P_NOWAITO` или `mode`) — это дескриптор процесса. Состояние выхода имеет значение 0, если процесс завершился обычным образом. Для состояния выхода можно задать ненулевое значение, если порожденный процесс специально вызывает процедуру `exit` с ненулевым аргументом. Если новый процесс не задал положительное состояние выхода в явном виде, положительное состояние выхода указывает на аварийный выход по отмене или прерыванию. Возвращаемое значение-1 указывает на ошибку (новый процесс не запущен). В этом случае `errno` имеет одно из следующих значений.  
  
 `E2BIG`  
 Длина списка аргументов превышает 1024 байта.  
  
 `EINVAL`  
Недопустимый аргумент `mode` .  
  
 `ENOENT`  
 Файл или путь не найден.  
  
 `ENOEXEC`  
 Указанный файл не является исполняемым или имеет недопустимый формат исполняемого файла.  
  
 `ENOMEM`  
 Недостаточно памяти для выполнения нового процесса.  
  
 Дополнительные сведения об этих и других кодах возврата см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Эти функции проверяют свои параметры. Если параметр `cmdname` или `arg0` является пустой строкой или пустым указателем, вызывается обработчик недопустимых параметров, как описано в статье [Parameter Validation](../../c-runtime-library/parameter-validation.md). Если продолжение выполнения разрешено, эти функции устанавливают для `errno` значение `EINVAL`и возвращают -1. Нет порожденных новых процессов.  
  
## <a name="remarks"></a>Примечания  
 Каждая из этих функций создает и выполняет новый процесс, передавая все аргументы командной строки как отдельные параметры.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_spawnl`|\<process.h>|  
|`_wspawnl`|\<stdio.h> или \<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Пример  
 См. пример в разделе [Функции _spawn, _wspawn](../../c-runtime-library/spawn-wspawn-functions.md).  
  
## <a name="see-also"></a>См. также  
 [Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)   
 [Функции _spawn, _wspawn](../../c-runtime-library/spawn-wspawn-functions.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [Функции _exec, _wexec](../../c-runtime-library/exec-wexec-functions.md)   
 [exit, _Exit, _exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [_flushall](../../c-runtime-library/reference/flushall.md)   
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [_onexit, _onexit_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [system, _wsystem](../../c-runtime-library/reference/system-wsystem.md)
