---
title: _putenv, _wputenv
ms.date: 11/04/2016
api_name:
- _putenv
- _wputenv
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
- api-ms-win-crt-environment-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _tputenv
- _wputenv
- _putenv
- wputenv
- tputenv
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
ms.openlocfilehash: 8fe699a476ea1dd09a6ce9922294bce398df16b2
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70949883"
---
# <a name="_putenv-_wputenv"></a>_putenv, _wputenv

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

*енвстринг*<br/>
Определение строки среды.

## <a name="return-value"></a>Возвращаемое значение

Возвращает 0 в случае успеха или-1 в случае ошибки.

## <a name="remarks"></a>Примечания

Функция **_putenv** добавляет новые переменные среды или изменяет значения существующих переменных среды. Переменные среды определяют среду, в которой выполняется процесс (например, путь поиска по умолчанию для библиотек, связываемых с программой). **_wputenv** — это версия **_putenv**для расширенных символов; Аргумент *енвстринг* для **_wputenv** является строкой расширенных символов.

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tputenv**|**_putenv**|**_putenv**|**_wputenv**|

Аргумент *енвстринг* должен быть указателем на строку вида *имя_переменной*=*value_string*, где *имя_переменной* — это имя переменной среды для добавления или изменения, а *value_string* — переменная значений. Если *VarName* уже является частью среды, ее значение заменяется на *value_string*; в противном случае новая переменная *VarName* и ее значение *value_string* добавляются в среду. Можно удалить переменную из среды, указав пустой *value_string*или иными словами, указав только *имя_переменной*=.

**_putenv** и **_wputenv** влияют только на локальную среду текущего процесса; их нельзя использовать для изменения среды командного уровня. Таким образом, эти функции работают только в структурах данных, доступных библиотеке среды выполнения, а не в сегменте среды, созданном для процесса операционной системой. При завершении текущего процесса среда возвращается на уровень вызывающего процесса (в большинстве случаев — на уровень операционной системы). Однако измененная среда может быть передана любым новым процессам, созданным с помощью **_spawn**, **_exec**или **System**, и эти новые процессы получают новые элементы, добавленные **_putenv** и **_wputenv**.

Не изменяйте запись в среде напрямую: вместо этого используйте **_putenv** или **_wputenv** , чтобы изменить его. В частности, прямые свободные элементы глобального массива **_environ []** могут привести к неправильному устранению памяти.

**getenv** и **_putenv** используют глобальную переменную **_environ** для доступа к таблице Environment; **_wgetenv** и **_wputenv** используют **_wenviron**. **_putenv** и **_wputenv** могут изменять значение **_environ** и **_wenviron**, тем самым делая аргумент **_envp** значением **Main** и аргументом **_wenvp** для **wmain**. Таким образом, для доступа к сведениям о среде безопаснее использовать **_environ** или **_wenviron** . Дополнительные сведения о связи **_putenv** и **_wputenv** с глобальными переменными см. в разделе [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md).

> [!NOTE]
> Семейства функций **_putenv** и **_getenv** не являются потокобезопасными. **_getenv** может вернуть указатель на строку, когда **_putenv** изменяет строку, вызывая случайные сбои. Убедитесь, что вызовы этих функций синхронизированы.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_putenv**|\<stdlib.h>|
|**_wputenv**|\<stdlib.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

Пример использования **_putenv**см. в разделе [getenv, _wgetenv](getenv-wgetenv.md).

## <a name="see-also"></a>См. также

[Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)<br/>
[getenv, _wgetenv](getenv-wgetenv.md)<br/>
[_searchenv, _wsearchenv](searchenv-wsearchenv.md)<br/>
