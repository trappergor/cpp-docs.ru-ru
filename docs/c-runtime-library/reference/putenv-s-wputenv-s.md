---
title: _putenv_s, _wputenv_s
ms.date: 4/2/2020
api_name:
- _wputenv_s
- _putenv_s
- _o__putenv_s
- _o__wputenv_s
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
- putenv_s
- wputenv_s
- _wputenv_s
- _putenv_s
helpviewer_keywords:
- wputenv_s function
- _putenv_s function
- environment variables, deleting
- putenv_s function
- _wputenv_s function
- environment variables, creating
- environment variables, modifying
ms.assetid: fbf51225-a8da-4b9b-9d7c-0b84ef72df18
ms.openlocfilehash: f0164feed05b409ba29ca713f11f4f3323dbaac3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338391"
---
# <a name="_putenv_s-_wputenv_s"></a>_putenv_s, _wputenv_s

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

*варимя*<br/>
Имя переменной среды.

*value_string*<br/>
Значение, которое будет задано для переменной среды.

## <a name="return-value"></a>Возвращаемое значение

Возвращает 0 в случае успешного выполнения операции или код ошибки.

### <a name="error-conditions"></a>Ситуации, которые могут привести к ошибке

|*варимя*|*value_string*|Возвращаемое значение|
|------------|-------------|------------------|
|**Null**|any|**EINVAL**|
|any|**Null**|**EINVAL**|

Если возникает одно из условий ошибки, эти функции вызывают обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение разрешено продолжать, эти функции возвращают **EINVAL** и устанавливают **errno** **в EINVAL.**

## <a name="remarks"></a>Remarks

Функция **_putenv_s** добавляет новые переменные среды или изменяет значения существующих переменных среды. Переменные среды определяют среду, в которой выполняется процесс (например, путь поиска по умолчанию для библиотек, связываемых с программой). **_wputenv_s** является широкохарактерным вариантом **_putenv_s;** *envstring* аргумент **_wputenv_s** является широкохарактерный строки.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tputenv_s**|**_putenv_s**|**_putenv_s**|**_wputenv_s**|

*varname* — это имя переменной среды, которая должна быть добавлена или изменена, и *value_string* значение переменной. Если *варимя* уже является частью окружающей среды, его значение заменяется *value_string;* в противном случае новая переменная *varname* и ее *value_string* добавляются в окружающую среду. Можно удалить переменную из среды, указав пустую строку (т.е. ") для *value_string.*

**_putenv_s** и **_wputenv_s** влияют только на окружающую среду, которая является локальной для нынешнего процесса; вы не можете использовать их для изменения среды командного уровня. Эти функции работают только в структурах данных, доступных библиотеке времени выполнения, а не в "сегменте" среды, созданном для процесса операционной системой. По завершении текущего процесса среда возвращается на уровень вызывающего процесса; в большинстве случаев это уровень операционной системы. Тем не менее, измененная среда может быть передана любым новым процессам, которые создаются **_spawn,** **_exec**или **системой,** и эти новые процессы получают любые новые элементы, которые добавляются **_putenv_s** и **_wputenv_s.**

Не изменяйте вход среды напрямую; вместо этого используйте **_putenv_s** или **_wputenv_s,** чтобы изменить его. В частности, прямое освобождение элементов глобального массива **_environ** может привести к обращению с недействительной памятью.

**getenv** и **_putenv_s** используют глобальную переменную **_environ** для доступа к таблице среды; **_wgetenv** и **_wputenv_s** используют **_wenviron.** **_putenv_s** и **_wputenv_s** могут изменить значение **_environ** и **_wenviron,** и тем самым признать недействительным *аргумент envp* к **основному** и **_wenvp** аргументу **wmain**. Поэтому безопаснее использовать **_environ** или **_wenviron** для доступа к информации об окружающей среде. Для получения дополнительной информации о взаимосвязи **_putenv_s** и **_wputenv_s** с глобальными переменными, см. [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md).

> [!NOTE]
> **_putenv_s** и **_getenv_s** семейства функций не являются безопасными для потоков. **_getenv_s** может вернуть указатель строки в то время как **_putenv_s** изменяет строку, и тем самым вызвать случайные сбои. Убедитесь, что вызовы этих функций синхронизированы.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_putenv_s**|\<stdlib.h>|
|**_wputenv_s**|\<stdlib.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

Для примера, который показывает, как использовать **_putenv_s,** [см. getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md).

## <a name="see-also"></a>См. также раздел

[Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)<br/>
[getenv, _wgetenv](getenv-wgetenv.md)<br/>
[_searchenv, _wsearchenv](searchenv-wsearchenv.md)<br/>
