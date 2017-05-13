---
title: "_spawnvpe, _wspawnvpe | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _spawnvpe
- _wspawnvpe
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
- _spawnvpe
- wspawnvpe
- spawnvpe
- _wspawnvpe
dev_langs:
- C++
helpviewer_keywords:
- _wspawnvpe function
- processes, creating
- _spawnvpe function
- processes, executing new
- wspawnvpe function
- process creation
- spawnvpe function
ms.assetid: 3db6394e-a955-4837-97a1-fab1db1e6092
caps.latest.revision: 16
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
ms.openlocfilehash: 5c6b6ce9e791ff0a514d5d5d04ba73a6de1b9c90
ms.contentlocale: ru-ru
ms.lasthandoff: 04/01/2017

---
# <a name="spawnvpe-wspawnvpe"></a>_spawnvpe, _wspawnvpe
Создает и выполняет новый процесс.  
  
> [!IMPORTANT]
>  Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
intptr_t _spawnvpe(  
   int mode,  
   const char *cmdname,  
   const char *const *argv,  
   const char *const *envp   
);  
intptr_t _wspawnvpe(  
   int mode,  
   const wchar_t *cmdname,  
   const wchar_t *const *argv,  
   const wchar_t *const *envp   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `mode`  
 Режим выполнения для вызывающего процесса  
  
 `cmdname`  
 Путь к выполняемому файлу  
  
 `argv`  
 Массив указателей на аргументы. Аргумент `argv`[0] обычно является указателем на путь в реальном режиме или на имя программы в защищенном режиме, а аргументы с `argv`[1] по `argv`[`n`] — это указатели на символьные строки, формирующие новый список аргументов. Аргумент `argv`[`n` +1] должен быть указателем `NULL` , отмечающим конец списка аргументов.  
  
 `envp`  
 Массив указателей на параметры среды  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращаемое значение синхронных функций `_spawnvpe` или `_wspawnvpe` (для параметра `_P_WAIT` указано значение `mode`) — это состояние завершения нового процесса. Возвращаемое значение асинхронной функции `_spawnvpe` или `_wspawnvpe` (для параметра `_P_NOWAIT` указано значение `_P_NOWAITO` или `mode`) — это дескриптор процесса. Состояние выхода имеет значение 0, если процесс завершился обычным образом. Для состояния выхода можно задать ненулевое значение, если порожденный процесс специально вызывает процедуру `exit` с ненулевым аргументом. Если новый процесс не задал положительное состояние выхода в явном виде, положительное состояние выхода указывает на аварийный выход по отмене или прерыванию. Возвращаемое значение-1 указывает на ошибку (новый процесс не запущен). В этом случае `errno` имеет одно из следующих значений:  
  
 `E2BIG`  
 Длина списка аргументов превышает 1024 байта  
  
 `EINVAL`  
Недопустимый аргумент  `mode`  
  
 `ENOENT`  
 Файл или путь не найден  
  
 `ENOEXEC`  
 Указанный файл не является исполняемым или имеет недопустимый формат исполняемого файла  
  
 `ENOMEM`  
 Недостаточно памяти для выполнения нового процесса  
  
 Дополнительные сведения об этих и других кодах возврата см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Примечания  
 Каждая из этих функций создает и выполняет новый процесс, передавая ему массив указателей на аргументы командной строки и массив указателей на параметры среды. Для поиска выполняемого файла в таких функциях используется переменная среды `PATH`.  
  
 Эти функции проверяют свои параметры. Если параметр `cmdname` или `argv` является пустым указателем, параметр `argv` указывает на пустой указатель или параметр `argv[0]` является пустой строкой, вызывается обработчик недопустимого параметра, как описано в статье [Проверка параметров](../../c-runtime-library/parameter-validation.md) . Если продолжение выполнения разрешено, эти функции устанавливают для `errno` значение `EINVAL`и возвращают -1. Нет порожденных новых процессов.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_spawnvpe`|\<stdio.h> или \<process.h>|  
|`_wspawnvpe`|\<stdio.h> или \<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Пример  
 См. пример в разделе [Функции _spawn, _wspawn](../../c-runtime-library/spawn-wspawn-functions.md).  
  
## <a name="see-also"></a>См. также  
 [abort](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [Функции _exec, _wexec](../../c-runtime-library/exec-wexec-functions.md)   
 [exit, _Exit, _exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [_flushall](../../c-runtime-library/reference/flushall.md)   
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [_onexit, _onexit_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [system, _wsystem](../../c-runtime-library/reference/system-wsystem.md)
