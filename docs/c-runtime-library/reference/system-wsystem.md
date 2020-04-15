---
title: system, _wsystem
ms.date: 4/2/2020
api_name:
- system
- _wsystem
- _o__wsystem
- _o_system
api_location:
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _tsystem
- _wsystem
helpviewer_keywords:
- _wsystem function
- wsystem function
- tsystem function
- _tsystem function
- system function
- commands, executing
- command interpreter
ms.assetid: 7d3df2b6-f742-49ce-bf52-012b0aee3df5
ms.openlocfilehash: 21ce04d30da80a40a1162dce06ff378150008766
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81362787"
---
# <a name="system-_wsystem"></a>system, _wsystem

Выполняет команду.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
int system(
   const char *command
);
int _wsystem(
   const wchar_t *command
);
```

### <a name="parameters"></a>Параметры

*Команды*<br/>
Команда для выполнения.

## <a name="return-value"></a>Возвращаемое значение

Если *команда* **NULL** и найден переводчик команды, возвращается значение ненулевого значения. Если переводчик команды не найден, возвращает 0 и устанавливает **errno** к **ENOENT**. Если *команда* не **является NULL,** **система** возвращает значение, возвращенное переводчиком команды. Она возвращает значение 0, только если интерпретатор команд возвращает значение 0. Значение возврата - 1 указывает на ошибку, и **errno** устанавливается на одно из следующих значений:

|||
|-|-|
| **E2BIG** | Список аргументов (который зависит от системы) слишком велик. |
| **ENOENT** | Интерпретатор команд не найден. |
| **ENOEXEC** | Файл интерпретатора команд не может быть выполнен из-за недопустимого формата. |
| **ENOMEM** | Недостаточно доступной памяти для выполнения команды; или доступная память повреждена; или существует недопустимый блок, что указывает на неправильное выделение памяти для процесса, который выполняет вызов. |

Дополнительные сведения об этих кодах возврата см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Remarks

Функция **системы** передает *команду* командному переводчику, который выполняет строку как команду операционной системы. **система** использует переменные среды **COMSPEC** и **PATH** для определения местонахождения командно-переводчика ФАЙЛа CMD.exe. Если *команда* **NULL,** функция просто проверяет, существует ли переводчик команды.

Вы должны явно флеш, с помощью [fflush](fflush.md) или [_flushall,](flushall.md)или закрыть любой поток, прежде чем вызвать **систему.**

**_wsystem** является широкохарактерным вариантом **системы;** *аргумент команды* для **_wsystem** является широкохарактерной строкой. В остальном эти функции ведут себя одинаково.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tsystem**|**система**|**система**|**_wsystem**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**система**|\<process.h> или \<stdlib.h>|
|**_wsystem**|\<process.h> или \<stdlib.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

Этот пример использует **систему** для TYPE текстовый файл.

```C
// crt_system.c

#include <process.h>

int main( void )
{
   system( "type crt_system.txt" );
}
```

### <a name="input-crt_systemtxt"></a>Входные данные: crt_system.txt

```Input
Line one.
Line two.
```

### <a name="output"></a>Выходные данные

```Output
Line one.
Line two.
```

## <a name="see-also"></a>См. также раздел

[Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)<br/>
[_exec, _wexec функции](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_flushall](flushall.md)<br/>
[Функции _spawn, _wspawn](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
