---
title: Глобальное состояние в CRT
description: Описывает, как общее глобальное состояние обрабатывается в универсальной среде выполнения C.
ms.date: 04/02/2020
helpviewer_keywords:
- CRT global state
ms.openlocfilehash: d1c787147ea3df36ce120837ef5b2c68b1bf58b1
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2020
ms.locfileid: "89554673"
---
# <a name="global-state-in-the-crt"></a>Глобальное состояние в CRT

Некоторые функции в универсальной среде выполнения C (UCRT) используют глобальное состояние. Например, `setlocale()` задает языковой стандарт для всей программы, который влияет на разделители цифр, текстовое кодовую страницу и т. д.

Глобальное состояние UCRT не является общим для приложений и ОС. Например, если приложение вызывает `setlocale()` , оно не влияет на языковой стандарт для всех компонентов ОС, использующих время выполнения C, или наоборот.

## <a name="os-specific-versions-of-crt-functions"></a>Версии функций CRT для конкретной ОС

В UCRT функции, взаимодействующие с глобальным состоянием, имеют функцию "двойника" с префиксом `_o_` . Пример:

- `setlocale()` влияет на глобальное состояние, относящееся к приложению.
- `_o_setlocale()` влияет на глобальное состояние, совместно используемое всеми компонентами ОС, но не с приложениями.

Единственное различие между этими функциями "двойника" заключается в том, что при чтении и записи глобального состояния CRT версии, зависящие от ОС (то есть версии, начинающиеся с `_o_` ), используют копию ОС глобального состояния вместо копии глобального состояния приложения.

Версии этих функций, специфичные для ОС, находятся в `ucrt.osmode.lib` . Например, версия для конкретной ОС `setlocale()` — `_o_setlocale()`

Существует два способа изолировать состояние CRT компонента из состояния CRT приложения:

- Статическая компоновка компонента с помощью параметров компилятора/MT (Release) или MTd (Debug). Дополнительные сведения см. в разделе [/MD,/MT,/LD](../build/reference/md-mt-ld-use-run-time-library.md). Обратите внимание, что статическая компоновка может значительно увеличить двоичный размер.
- Начиная с Windows 10 20H2, получить изоляцию состояния CRT, динамически связываясь с CRT, но вызвав экспорты в режиме операционной системы (функции, начинающиеся с _o_). Чтобы вызвать экспорты в режиме операционной системы, статическая компоновка как и прежде, но игнорировать статический UCRT с помощью параметра компоновщика `/NODEFAULTLIB:libucrt.lib` (Release) или `/NODEFAULTLIB:libucrtd.lib` (Debug) см. Дополнительные сведения о параметре [/NODEFAULTLIB (игнорировать библиотеки)](../build/reference/nodefaultlib-ignore-libraries.md) . И добавьте `ucrt.osmode.lib` к входным данным компоновщика.

> [!Note]
> В исходном коде напишите `setlocale()` , а не `_o_setlocale()` . При связывании с `ucrt.osmode.lib` Компоновщик автоматически подставляет версию функции, зависящую от ОС. То есть `setlocale()` будет заменено на `_o_setlocale()` .

Связывание `ucrt.osmode.lib` используется для отключения некоторых вызовов UCRT, доступных только в режиме приложения. Попытка вызова этих данных приведет к ошибке компоновки.

## <a name="global-state-affected-by-appos-separation"></a>Глобальное состояние, затронутое разделением приложения или ОС

Глобальное состояние, затронутое разделением состояния приложения и ОС, включает:

- [Данные языкового стандарта](locale.md)
- Обработчики сигналов, заданные [сигналом](reference/signal.md)
- Подпрограммы завершения заданы методом [Terminate](reference/set-terminate-crt.md)
- [пере_doserrno](errno-doserrno-sys-errlist-and-sys-nerr.md)
- Состояние генерации случайных чисел, используемое [СЛЧИС](reference/rand.md) и [srand](reference/srand.md)
- Функции, возвращающие буфер, который пользователю не нужно выпустить:   [strtok, wcstok, _mbstok](reference/strtok-strtok-l-wcstok-wcstok-l-mbstok-mbstok-l.md) [tmpnam, _wtmpnam](reference/tempnam-wtempnam-tmpnam-wtmpnam.md) [asctime, _wasctime](reference/asctime-wasctime.md) [gmtime, _gmtime32, _gmtime64](reference/gmtime-gmtime32-gmtime64.md) [_fcvt](reference/fcvt.md) [_ecvt](reference/ecvt.md) [strerror, _strerror, _wcserror, __wcserror](reference/strerror-strerror-wcserror-wcserror.md)
- Буфер [, используемый _putch _putwch](reference/putch-putwch.md)
- [_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler](reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)
- [_set_new_handler](reference/set-new-handler.md) и [_set_new_mode](reference/set-new-mode.md)
- [фмоде] (text-and-binary-mode-file-i-o.md)
- [Сведения о часовом поясе](time-management.md)

## <a name="see-also"></a>Дополнительно

[Справочник по библиотеке времени выполнения C](c-run-time-library-reference.md)
