---
title: system, _wsystem
ms.date: 11/04/2016
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
helpviewer_keywords:
- _wsystem function
- wsystem function
- tsystem function
- _tsystem function
- system function
- commands, executing
- command interpreter
ms.assetid: 7d3df2b6-f742-49ce-bf52-012b0aee3df5
ms.openlocfilehash: 46c4949fcc8cfbe4a3477e66b57d8fc6fc97ed73
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62259096"
---
# <a name="system-wsystem"></a>system, _wsystem

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

*command*<br/>
Команда для выполнения.

## <a name="return-value"></a>Возвращаемое значение

Если *команда* — **NULL** и найден интерпретатор команд, возвращает ненулевое значение. Если интерпретатор команд не найден, возвращается значение 0 и задает **errno** для **ENOENT**. Если *команда* не **NULL**, **системы** возвращает значение, возвращаемое интерпретатором команд. Она возвращает значение 0, только если интерпретатор команд возвращает значение 0. Возвращаемое значение, равное - 1 указывает на ошибку, и **errno** присваивается одно из следующих значений:

|||
|-|-|
| **E2BIG** | Список аргументов (который зависит от системы) слишком велик. |
| **ENOENT** | Интерпретатор команд не найден. |
| **ENOEXEC** | Файл интерпретатора команд не может быть выполнен из-за недопустимого формата. |
| **ENOMEM** | Недостаточно доступной памяти для выполнения команды; или доступная память повреждена; или существует недопустимый блок, что указывает на неправильное выделение памяти для процесса, который выполняет вызов. |

Дополнительные сведения об этих кодах возврата см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

**Системы** функция передает *команда* интерпретатору команд, который выполняет эту строку как команду операционной системы. **система** использует **COMSPEC** и **путь** переменные среды, чтобы найти интерпретатор команд файла CMD.exe. Если *команда* — **NULL**, функция только проверяет, существует ли интерпретатор команд.

Необходимо явно очистить, с помощью [fflush](fflush.md) или [_flushall](flushall.md), или закрыть все потоки, перед вызовом метода **системы**.

**_wsystem** — это двухбайтовая версия **системы**; *команда* аргумент **_wsystem** — строка расширенных символов. В остальном эти функции ведут себя одинаково.

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tsystem**|**system**|**system**|**_wsystem**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**system**|\<process.h> или \<stdlib.h>|
|**_wsystem**|\<process.h> или \<stdlib.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

В этом примере используется **системы** для ввода в текстовый файл.

```C
// crt_system.c

#include <process.h>

int main( void )
{
   system( "type crt_system.txt" );
}
```

### <a name="input-crtsystemtxt"></a>Входные данные: crt_system.txt

```Input
Line one.
Line two.
```

### <a name="output"></a>Вывод

```Output
Line one.
Line two.
```

## <a name="see-also"></a>См. также

[Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)<br/>
[Функции _exec, _wexec](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_flushall](flushall.md)<br/>
[Функции _spawn, _wspawn](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
