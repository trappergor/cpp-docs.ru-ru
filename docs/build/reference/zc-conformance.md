---
title: /Zc (соответствие)
description: Параметры компилятора/Zc соответствия позволяют включить или отключить поддержку согласования или обратной совместимости.
ms.date: 09/10/2020
helpviewer_keywords:
- /Zc compiler options [C++]
- -Zc compiler options [C++]
- Conformance compiler options
- Zc compiler options [C++]
ms.assetid: db1cc175-6e93-4a2e-9396-c3725d2d8f71
ms.openlocfilehash: 13e06cd75f1ee684c2ee1ad6239aeb77b805675e
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "90041527"
---
# <a name="zc-conformance"></a>`/Zc` Соответствия

Параметры компилятора можно использовать **`/Zc`** для указания стандартного или конкретного поведения компилятора, характерного для Microsoft.

## <a name="syntax"></a>Синтаксис

> **`/Zc:`**_параметр_{,_параметр_}

## <a name="remarks"></a>Комментарии

Когда Visual Studio реализовала расширение для C или C++, несовместимое со стандартом, можно использовать **`/Zc`** параметр соответствия, чтобы указать стандартное соответствие или поведение, специфическое для Microsoft. Для некоторых параметров поведение по умолчанию зависит от Майкрософт, чтобы предотвратить крупномасштабные критические изменения в существующем коде. В других случаях по умолчанию используется стандартное поведение, в котором улучшения безопасности, производительности или совместимости перевешивают затраты на критические изменения. Значение по умолчанию для каждого параметра соответствия может измениться в более новых версиях Visual Studio. Дополнительные сведения о каждом параметре соответствия см. в разделе, посвященном конкретному параметру. [`/permissive-`](permissive-standards-conformance.md)Параметр компилятора неявно задает параметры соответствия, которые по умолчанию не заданы в соответствии с установленным параметром соответствия.

Ниже приведены **`/Zc`** параметры компилятора.

| Параметр | Поведение |
|--|--|
| [`/Zc:alignedNew`](zc-alignednew.md) | Включить динамическое выделение в C++ 17 по рассогласованию (включено по умолчанию в C++ 17). |
| [`/Zc:auto`](zc-auto-deduce-variable-type.md) | Применение нового стандартного значения C++ для **`auto`** (включено по умолчанию). |
| [`/Zc__cplusplus`](zc-cplusplus.md) | Включите `__cplusplus` макрос, чтобы сообщить о поддерживаемом стандарте (отключено по умолчанию). |
| [`/Zc:externConstexpr`](zc-externconstexpr.md) | Включить внешнюю компоновку для **`constexpr`** переменных (по умолчанию отключено). |
| [`/Zc:forScope`](zc-forscope-force-conformance-in-for-loop-scope.md) | Применять стандартные **`for`** правила области C++ (по умолчанию включено). |
| [`/ZcimplicitNoexcept`](zc-implicitnoexcept-implicit-exception-specifiers.md) | Включите неявное значение **`noexcept`** в обязательных функциях (включено по умолчанию). |
| [`/Zc:inline`](zc-inline-remove-unreferenced-comdat.md) | Удалите неиспользуемую функцию или данные, если они имеют значение COMDAT или только внутренние компоновки (отключено по умолчанию). |
| [`/Zc:noexceptTypes`](zc-noexcepttypes.md) | Применение правил C++ 17 **`noexcept`** (включено по умолчанию в c++ 17 или более поздней версии). |
| [`/Zc:preprocessor`](zc-preprocessor.md) | Используйте новый предпроцессорный препроцессор (по умолчанию отключен, за исключением C11/C17). |
| [`/Zc:referenceBinding`](zc-referencebinding-enforce-reference-binding-rules.md) | Временная операция определяемого пользователем типа не будет привязана к неконстантной ссылке lvalue (по умолчанию отключена). |
| [`/Zc:rvalueCast`](zc-rvaluecast-enforce-type-conversion-rules.md) | Применять стандартные правила явного преобразования типов C++ (по умолчанию отключено). |
| [`/Zc:sizedDealloc`](zc-sizeddealloc-enable-global-sized-dealloc-functions.md) | Включить глобальные функции выделения размера в C++ 14 (включено по умолчанию). |
| [`/Zc:strictStrings`](zc-strictstrings-disable-string-literal-type-conversion.md) | Отключите строку — литерал `char*` или `wchar_t*` Преобразование (по умолчанию отключено). |
| [`/Zc:ternary`](zc-ternary.md) | Применение правил условного оператора к типам операндов (по умолчанию отключено). |
| [`/Zc:threadSafeInit`](zc-threadsafeinit-thread-safe-local-static-initialization.md) | Включите потокобезопасную локальную статическую инициализацию (по умолчанию). |
| [`/Zc:throwingNew`](zc-throwingnew-assume-operator-new-throws.md) | Предположим **`operator new`** , что вызывается сбой (по умолчанию отключено). |
| [`/Zc:trigraphs`](zc-trigraphs-trigraphs-substitution.md) | Включить триграфов (устарело, по умолчанию отключено). |
| [`/Zc:twoPhase`](zc-twophase.md) | Используйте несоответствие поведения синтаксического анализа шаблона (по умолчанию соответствует). |
| [`/Zc:wchar_t`](zc-wchar-t-wchar-t-is-native-type.md) | **`wchar_t`** является собственным типом, а не typedef (on по умолчанию). |

Дополнительные сведения о вопросах соответствия в Visual C++ см. в статье [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).

## <a name="see-also"></a>См. также раздел

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора КОМПИЛЯТОРОМ MSVC](compiler-command-line-syntax.md)
