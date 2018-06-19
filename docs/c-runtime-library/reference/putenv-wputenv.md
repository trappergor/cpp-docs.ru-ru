---
title: _putenv, _wputenv | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _putenv
- _wputenv
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
- api-ms-win-crt-environment-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _tputenv
- _wputenv
- _putenv
- wputenv
- tputenv
dev_langs:
- C++
helpviewer_keywords:
- _putenv function
- environment variables, deleting
- putenv function
- tputenv function
- environment variables, creating
- wputenv function
- _wputenv function
- _tputenv function
- environment variables, modifying
ms.assetid: 9ba9b7fd-276e-45df-8420-d70c4204b8bd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fc7841963584bef19faf60de0112eeea25cb7ffd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32403977"
---
# <a name="putenv-wputenv"></a>_putenv, _wputenv

Создает, изменяет или удаляет переменные среды. Существуют более безопасные версии этих функций; см. статью [_putenv_s, _wputenv_s](putenv-s-wputenv-s.md).

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
int _putenv(
   const char *envstring
);
int _wputenv(
   const wchar_t *envstring
);
```

### <a name="parameters"></a>Параметры

*envstring*<br/>
Определение строки среды.

## <a name="return-value"></a>Возвращаемое значение

Возвращает 0 в случае успеха или значение -1 в случае ошибки.

## <a name="remarks"></a>Примечания

**_Putenv** функция добавляет новые переменные среды или изменяет значения существующих переменных среды. Переменные среды определяют среду, в которой выполняется процесс (например, путь поиска по умолчанию для библиотек, связываемых с программой). **_wputenv** — это двухбайтовая версия **_putenv**; *envstring* аргумент **_wputenv** представляет собой строку расширенных символов.

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tputenv**|**_putenv**|**_putenv**|**_wputenv**|

*Envstring* аргумент должен быть указателем на строку вида *varname*=*строка_значения*, где *varname* — Имя добавляемой или изменяемой переменной среды и *строка_значения* имеет значение переменной. Если *varname* уже является частью среды, ее значение заменяется значением *строка_значения*; в противном случае новый *varname* переменной и ее *строка_значения*  значения добавляются в среду. Можно удалить переменную среды, указав пустой *строка_значения*, или иными словами, указав только *varname*=.

**_putenv** и **_wputenv** затрагивают только локальную среду текущего процесса; их нельзя использовать для изменения среды командного уровня. Таким образом, эти функции работают только в структурах данных, доступных библиотеке среды выполнения, а не в сегменте среды, созданном для процесса операционной системой. При завершении текущего процесса среда возвращается на уровень вызывающего процесса (в большинстве случаев — на уровень операционной системы). Однако измененную среду можно передать любым новым процессам, созданные **_spawn**, **_exec**, или **системы**, и эти новые процессы получат все новые элементы, добавленные **_putenv** и **_wputenv**.

Не изменяйте запись среды напрямую: вместо этого используйте **_putenv** или **_wputenv** изменить его. В частности, непосредственное освобождение элементов **[] _environ** глобального массива может привести к адресации недопустимой памяти.

**getenv** и **_putenv** используют глобальную переменную **_environ** для доступа к таблице среды; **_wgetenv** и **_wputenv** использовать **_wenviron**. **_putenv** и **_wputenv** может изменить значение **_environ** и **_wenviron**, таким образом делая недействительным **_envp** Аргумент **основной** и **_wenvp** аргумент **wmain**. Таким образом, это безопаснее использовать **_environ** или **_wenviron** для доступа к данным среды. Дополнительные сведения о связи функций **_putenv** и **_wputenv** с глобальными переменными см. в разделе [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md).

> [!NOTE]
> **_Putenv** и **_getenv** семейства функций не являются потокобезопасными. **_getenv** может вернуть указатель строки при **_putenv** изменяет строку, вызывая случайные сбои. Убедитесь, что вызовы этих функций синхронизированы.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_putenv**|\<stdlib.h>|
|**_wputenv**|\<stdlib.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

Пример использования **_putenv**, в разделе [getenv, _wgetenv](getenv-wgetenv.md).

## <a name="see-also"></a>См. также

[Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)<br/>
[getenv, _wgetenv](getenv-wgetenv.md)<br/>
[_searchenv, _wsearchenv](searchenv-wsearchenv.md)<br/>
