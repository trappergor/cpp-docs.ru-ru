---
title: "system, _wsystem | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- system
- _wsystem
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _tsystem
- _wsystem
dev_langs: C++
helpviewer_keywords:
- _wsystem function
- wsystem function
- tsystem function
- _tsystem function
- system function
- commands, executing
- command interpreter
ms.assetid: 7d3df2b6-f742-49ce-bf52-012b0aee3df5
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1c470717d48836fd405e98f5fccca222e87a9c33
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="system-wsystem"></a>system, _wsystem
Выполняет команду.  
  
> [!IMPORTANT]
>  Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int system(  
   const char *command   
);  
int _wsystem(  
   const wchar_t *command   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `command`  
 Команда для выполнения.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Если параметр `command` имеет значение `NULL` и найден интерпретатор команд, возвращает ненулевое значение. Если интерпретатор команд не найден, возвращает значение 0 и задает для параметра `errno` значение `ENOENT`. Если параметр `command` не равен `NULL`, то функция `system` возвращает значение, возвращаемое интерпретатором команд. Она возвращает значение 0, только если интерпретатор команд возвращает значение 0. Возвращаемое значение - 1 указывает на ошибку, и `errno` присваивается одно из следующих значений:  
  
 `E2BIG`  
 Список аргументов (который зависит от системы) слишком велик.  
  
 `ENOENT`  
 Интерпретатор команд не найден.  
  
 `ENOEXEC`  
 Файл интерпретатора команд не может быть выполнен из-за недопустимого формата.  
  
 `ENOMEM`  
 Недостаточно доступной памяти для выполнения команды; или доступная память повреждена; или существует недопустимый блок, что указывает на неправильное выделение памяти для процесса, который выполняет вызов.  
  
 Дополнительные сведения об этих кодах возврата см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Примечания  
 Функция `system` передает параметр `command` интерпретатору команд, который выполняет эту строку как команду операционной системы. Для поиска файла интерпретатора команд CMD.exe функция `system` использует переменные среды `COMSPEC` и `PATH`. Если параметр `command` имеет значение `NULL`, функция только проверяет, существует ли интерпретатор команд.  
  
 Перед вызовом функции `fflush` необходимо явно очистить (с помощью функции `_flushall` или `system`) или закрыть все потоки.  
  
 `_wsystem` — это версия `system` с расширенными символами; аргумент `command` для `_wsystem` — строка расширенных символов. В остальном эти функции ведут себя одинаково.  
  
### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tsystem`|`system`|`system`|`_wsystem`|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`system`|\<process.h> или \<stdlib.h>|  
|`_wsystem`|\<process.h> или \<stdlib.h> или \<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Пример  
 В этом примере функция `system` используется для печати (TYPE) текстового файла.  
  
```  
// crt_system.c  
  
#include <process.h>  
  
int main( void )  
{  
   system( "type crt_system.txt" );  
}  
```  
  
## <a name="input-crtsystemtxt"></a>Входные данные: crt_system.txt  
  
```  
Line one.  
Line two.  
```  
  
### <a name="output"></a>Вывод  
  
```  
Line one.  
Line two.  
```  
  
## <a name="see-also"></a>См. также  
 [Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)   
 [Функции _exec, _wexec](../../c-runtime-library/exec-wexec-functions.md)   
 [exit, _Exit, _exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [_flushall](../../c-runtime-library/reference/flushall.md)   
 [Функции _spawn, _wspawn](../../c-runtime-library/spawn-wspawn-functions.md)