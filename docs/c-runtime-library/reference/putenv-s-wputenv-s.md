---
title: _putenv_s, _wputenv_s | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wputenv_s
- _putenv_s
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
apitype: DLLExport
f1_keywords:
- putenv_s
- wputenv_s
- _wputenv_s
- _putenv_s
dev_langs:
- C++
helpviewer_keywords:
- wputenv_s function
- _putenv_s function
- environment variables, deleting
- putenv_s function
- _wputenv_s function
- environment variables, creating
- environment variables, modifying
ms.assetid: fbf51225-a8da-4b9b-9d7c-0b84ef72df18
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e84d7a68530a748c9b1ad7c553fad80ed4e7c86b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="putenvs-wputenvs"></a>_putenv_s, _wputenv_s

Создает, изменяет или удаляет переменные среды. Это версии функций [_putenv, _wputenv](putenv-wputenv.md) с усовершенствованной безопасностью, как описано в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
errno_t _putenv_s(
   const char *varname,
   const char *value_string
);
errno_t _wputenv_s(
   const wchar_t *varname,
   const wchar_t *value_string
);
```

### <a name="parameters"></a>Параметры

*varname*<br/>
Имя переменной среды.

*строка_значения*<br/>
Значение, которое будет задано для переменной среды.

## <a name="return-value"></a>Возвращаемое значение

Возвращает 0 в случае успешного выполнения операции или код ошибки.

### <a name="error-conditions"></a>Условия ошибок

|*varname*|*строка_значения*|Возвращаемое значение|
|------------|-------------|------------------|
|**NULL**|any|**EINVAL**|
|any|**NULL**|**EINVAL**|

Если возникает одно из условий ошибки, эти функции вызывают обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции возвращают **EINVAL** и задайте **errno** для **EINVAL**.

## <a name="remarks"></a>Примечания

**_Putenv_s** функция добавляет новые переменные среды или изменяет значения существующих переменных среды. Переменные среды определяют среду, в которой выполняется процесс (например, путь поиска по умолчанию для библиотек, связываемых с программой). **_wputenv_s** — это двухбайтовая версия **_putenv_s**; *envstring* аргумент **_wputenv_s** представляет собой строку расширенных символов.

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tputenv_s**|**_putenv_s**|**_putenv_s**|**_wputenv_s**|

*VarName* — имя добавляемой или изменяемой переменной среды и *строка_значения* имеет значение переменной. Если *varname* уже является частью среды, ее значение заменяется значением *строка_значения*; в противном случае новый *varname* переменной и ее *строка_значения*  добавляются в среду. Можно удалить переменную среды, указав пустую строку (то есть «») для *строка_значения*.

**_putenv_s** и **_wputenv_s** затрагивают только локальную среду текущего процесса; их нельзя использовать для изменения среды командного уровня. Эти функции работают только в структурах данных, доступных библиотеке времени выполнения, а не в "сегменте" среды, созданном для процесса операционной системой. По завершении текущего процесса среда возвращается на уровень вызывающего процесса; в большинстве случаев это уровень операционной системы. Однако измененную среду можно передать любым новым процессам, созданным **_spawn**, **_exec**, или **системы**, и эти новые процессы получат все новые элементы, которые являются добавленные **_putenv_s** и **_wputenv_s**.

Не изменяйте запись среды напрямую; Вместо этого используйте **_putenv_s** или **_wputenv_s** изменить его. В частности, непосредственное освобождение элементов **[] _environ** глобального массива может привести к недопустимой памяти адресацию.

**getenv** и **_putenv_s** используют глобальную переменную **_environ** для доступа к таблице среды; **_wgetenv** и **_wputenv_s** использовать **_wenviron**. **_putenv_s** и **_wputenv_s** может изменить значение **_environ** и **_wenviron**и тем самым сделать недействительным *envp*аргумент **основной** и **_wenvp** аргумент **wmain**. Таким образом, это безопаснее использовать **_environ** или **_wenviron** для доступа к данным среды. Дополнительные сведения о связи функций **_putenv_s** и **_wputenv_s** с глобальными переменными см. в разделе [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md).

> [!NOTE]
> **_Putenv_s** и **_getenv_s** семейства функций не являются потокобезопасными. **_getenv_s** может вернуть указатель строки при **_putenv_s** изменения строки и тем самым может вызвать случайные сбои. Убедитесь, что вызовы этих функций синхронизированы.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_putenv_s**|\<stdlib.h>|
|**_wputenv_s**|\<stdlib.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

Пример, в котором показано, как использовать **_putenv_s**, в разделе [getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md).

## <a name="see-also"></a>См. также

[Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)<br/>
[getenv, _wgetenv](getenv-wgetenv.md)<br/>
[_searchenv, _wsearchenv](searchenv-wsearchenv.md)<br/>
