---
title: Глобальное состояние в CRT
ms.date: 04/02/2020
helpviewer_keywords:
- CRT global state
ms.openlocfilehash: 487418da104b2edbc45b5d3a664e4385394ada31
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377602"
---
# <a name="global-state-in-the-crt"></a>Глобальное состояние в CRT

Некоторые функции в Универсальном C Runtime (UCRT) используют глобальное состояние. Например, `setlocale()` устанавливается локаль для всей программы, которая влияет на сепараторы цифр, страницу текстового кода и так далее.

Глобальное состояние UCRT не распределяется между приложениями и ОС. Например, если приложение `setlocale()`вызывает вызовы, это не повлияет на локаль для любых компонентов ОС, которые используют время выполнения C, или наоборот.

## <a name="os-specific-versions-of-crt-functions"></a>ОС-специфические версии функций CRT

В UCRT функции, взаимодействующие с глобальным государством, имеют `_o_`функцию «двойника», прикреплую к . Пример:

    `setlocale()` affects global state specific to the app.
    `_o_setlocale()` affects global state shared by all OS components, but not apps.

Единственное различие между этими "двойными" функциями заключается в том, что, когда они читают/пишут `_o_`глобальное состояние CRT, ос-специфические версии (т.е. версии, которые начинаются с) используют копию ОС глобального государства вместо копии приложения глобального государства.

ОС-специфические версии `ucrt.osmode.lib`этих функций находятся в . Например, конкретная версия `setlocale()` ОС`_o_setlocale()`

Существует два способа изолировать состояние CRT компонента от состояния CRT приложения:

- Статически связать компонент с помощью компиляторов /MT (релиз) или MTd (отладка). Подробности в материале [:MD, /MT, /LD](https://docs.microsoft.com/cpp/build/reference/md-mt-ld-use-run-time-library?view=vs-2019). Обратите внимание, что статическое соединение может значительно увеличить двоичный размер.
- Начиная с Windows 10 20H2, получить изоляцию состояния CRT динамически ссылок на CRT, но вызов OS-режим экспорта (функции, которые начинаются с _o_). Чтобы вызвать экспорт OS-режима, статично ссылку, как и раньше, но игнорировать статический UCRT с помощью опции `/NODEFAULTLIB:libucrt.lib` linker (релиз) или `/NODEFAULTLIB:libucrtd.lib` (отладка) См/ [NODEFAULTLIB (Игнорировать библиотеки)](https://docs.microsoft.com/cpp/build/reference/nodefaultlib-ignore-libraries?view=vs-2019) для деталей. И `ucrt.osmode.lib` добавить к вхотворитель ный linker.

> [!Note]
> В исходном `setlocale()`коде, писать , не `_o_setlocale()`. При связях `ucrt.osmode.lib`с , связующий автоматически заменит ОС-специфической версии функции. То есть, `setlocale()` будет заменен `_o_setlocale()`.

Ссылка `ucrt.osmode.lib` на отстраняет некоторые вызовы UCRT, которые доступны только в режиме приложения. Попытка вызова этих вызовов приведет к ошибке ссылки.

## <a name="global-state-affected-by-appos-separation"></a>Глобальное состояние, пострадавшее от разделения приложений/ОС

Глобальное состояние, пострадавшее от разделения состояния приложения и ОС, включает в себя:

- [Данные о локализации](locale.md)
- Обработчики сигнала, установленные [сигналом](reference/signal.md)
- Процедуры прекращения, установленные [завершением](reference/set-terminate-crt.md)
- [errno и _doserrno](errno-doserrno-sys-errlist-and-sys-nerr.md)
- Состояние генерации случайных чичестей, используемое [рандом](reference/rand.md) и [срандом](reference/srand.md)
- Функции, которые возвращают буфер, который пользователь не должен выпускать: [strtok, wcstok, _mbstok](reference/strtok-strtok-l-wcstok-wcstok-l-mbstok-mbstok-l.md) [Tmpnam, _wtmpnam](reference/tempnam-wtempnam-tmpnam-wtmpnam.md) [asctime, _wasctime](reference/asctime-wasctime.md) [gmtime, _gmtime32, _gmtime64](reference/gmtime-gmtime32-gmtime64.md) [_fcvt](reference/fcvt.md) [_ecvt](reference/ecvt.md) [strerror, _strerror, _wcserror, __wcserror](reference/strerror-strerror-wcserror-wcserror.md)
- Буфер, используемый [_putch, _putwch](reference/putch-putwch.md)
- [_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler](reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)
- [_set_new_handler](reference/set-new-handler.md) и [_set_new_mode](reference/set-new-mode.md)
- (фмод) (text-and-binary-mode-file-i-o.md)
- [Сведения часового пояса](time-management.md)

## <a name="see-also"></a>См. также раздел

[C Ссылка на библиотеку Run-Time](c-run-time-library-reference.md)