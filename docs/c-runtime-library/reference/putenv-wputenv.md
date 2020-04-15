---
title: _putenv, _wputenv
ms.date: 4/2/2020
api_name:
- _putenv
- _wputenv
- _o__putenv
- _o__wputenv
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 3e74959e6c6cdb2e27ce0d68ba40d02d64949904
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81333031"
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

*envstring*<br/>
Определение строки среды.

## <a name="return-value"></a>Возвращаемое значение

Возврат 0 в случае ошибки или -1.

## <a name="remarks"></a>Remarks

Функция **_putenv** добавляет новые переменные среды или изменяет значения существующих переменных среды. Переменные среды определяют среду, в которой выполняется процесс (например, путь поиска по умолчанию для библиотек, связываемых с программой). **_wputenv** является широкохарактерным вариантом **_putenv;** *envstring* аргумент **_wputenv** является широкохарактерный строки.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tputenv**|**_putenv**|**_putenv**|**_wputenv**|

Аргумент *envstring* должен быть указателем на строку *варнах*=формы*value_string,* где *варимя* — это имя переменной среды, которая должна быть добавлена или изменена, и *value_string* значение переменной. Если *варимя* уже является частью окружающей среды, его значение заменяется *value_string;* в противном случае новая переменная *varname* и ее *value_string* значение добавляются к окружающей среде. Вы можете удалить переменную из среды, указав пустую *value_string,* или, другими словами, указав только *варимя*.

**_putenv** и **_wputenv** влияют только на окружающую среду, которая является локальной для нынешнего процесса; вы не можете использовать их для изменения среды командного уровня. Таким образом, эти функции работают только в структурах данных, доступных библиотеке среды выполнения, а не в сегменте среды, созданном для процесса операционной системой. При завершении текущего процесса среда возвращается на уровень вызывающего процесса (в большинстве случаев — на уровень операционной системы). Тем не менее, измененная среда может быть передана любым новым процессам, созданным **_spawn,** **_exec**или **системой,** и эти новые процессы получают любые новые элементы, добавленные **_putenv** и **_wputenv.**

Не изменяйте запись среды напрямую: вместо этого используйте **_putenv** или **_wputenv,** чтобы изменить ее. В частности, прямое освобождение элементов глобального массива **_environ** может привести к обращению недействительной памяти.

**getenv** и **_putenv** используют глобальную переменную **_environ** для доступа к таблице среды; **_wgetenv** и **_wputenv** используют **_wenviron.** **_putenv** и **_wputenv** могут изменить значение **_environ** и **_wenviron,** тем самым отменяя **_envp** аргумент **к основному** и **_wenvp** аргументу **wmain.** Поэтому безопаснее использовать **_environ** или **_wenviron** для доступа к информации об окружающей среде. Более подробную информацию о связи **_putenv** и **_wputenv** с глобальными переменными можно [_environ, _wenviron.](../../c-runtime-library/environ-wenviron.md)

> [!NOTE]
> **_putenv** и **_getenv** семейства функций не являются безопасными для потоков. **_getenv** может вернуть указатель строки, в то время как **_putenv** изменяет строку, вызывая случайные сбои. Убедитесь, что вызовы этих функций синхронизированы.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_putenv**|\<stdlib.h>|
|**_wputenv**|\<stdlib.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

Для примера того, как использовать **_putenv,** [см. getenv, _wgetenv](getenv-wgetenv.md).

## <a name="see-also"></a>См. также раздел

[Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)<br/>
[getenv, _wgetenv](getenv-wgetenv.md)<br/>
[_searchenv, _wsearchenv](searchenv-wsearchenv.md)<br/>
