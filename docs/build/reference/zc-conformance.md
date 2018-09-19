---
title: /Zc (соответствие) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /zc
dev_langs:
- C++
helpviewer_keywords:
- /Zc compiler options [C++]
- -Zc compiler options [C++]
- Conformance compiler options
- Zc compiler options [C++]
ms.assetid: db1cc175-6e93-4a2e-9396-c3725d2d8f71
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3fd2ec208e872e05f8329bf5e077a74403d0c612
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45716057"
---
# <a name="zc-conformance"></a>/Zc (соответствие)

Можно использовать **/Zc** параметры компилятора, чтобы задать поведение компилятора standard или характерные для Майкрософт.

## <a name="syntax"></a>Синтаксис

> **/ Zc:**_параметр_{,_параметр_}

## <a name="remarks"></a>Примечания

При реализации расширения для C или C++, который не совместим со стандартом Visual Studio можно использовать `/Zc` параметр соответствия, чтобы указать поведение соответствующих standard или характерные для Майкрософт. Для некоторых параметров характерные для Майкрософт поведение используется по умолчанию, во избежание крупномасштабных критические изменения в существующий код. В других случаях значение по умолчанию является стандартное поведение, где усовершенствования в безопасности, производительности и совместимости превышает стоимость критические изменения. Значение по умолчанию каждый параметр соответствие может измениться в более новых версиях Visual Studio. Дополнительные сведения о каждом параметре соответствия см. в разделе, для конкретного параметра. [/ Permissive-](permissive-standards-conformance.md) параметр компилятора неявно задает параметры соответствия, не заданных по умолчанию для их параметров соответствует стандартам.

Это `/Zc` параметры компилятора:

|Параметр|Поведение|
|---|---|
|[alignedNew\[-\]](zc-alignednew.md)|Включить C ++ 17 динамического распределения (включен по умолчанию в C ++ 17).|
|[Авто\[-\]](zc-auto-deduce-variable-type.md)|Применить новое значение стандартного C++ для `auto` (на по умолчанию).|
|[__cplusplus\[-\]](zc-cplusplus.md)|Включить **__cplusplus** макрос для отчета, поддерживается стандарт (отключено по умолчанию).|
|[externConstexpr\[-\]](zc-externconstexpr.md)|Включить внешнюю компоновку для `constexpr` переменные (отключено по умолчанию).|
|[forScope\[-\]](zc-forscope-force-conformance-in-for-loop-scope.md)|Применять стандарт C++ `for` правила области видимости (на по умолчанию).|
|[implicitNoexcept\[-\]](zc-implicitnoexcept-implicit-exception-specifiers.md)|Включить неявное `noexcept` для требуемых функций (на по умолчанию).|
|[встроенный\[-\]](zc-inline-remove-unreferenced-comdat.md)|Удалите неиспользуемые функции или данные, если он COMDAT или используют только внутреннюю компоновку (отключено по умолчанию).|
|[noexceptTypes\[-\]](zc-noexcepttypes.md)|Применять правила noexcept C ++ 17 (на по умолчанию в C ++ 17 или более поздней версии).|
|[referenceBinding\[-\]](zc-referencebinding-enforce-reference-binding-rules.md)|Временный определяемого пользователем ТИПА не будет привязываться к ссылкой lvalue неконстантной (отключено по умолчанию).|
|[rvalueCast\[-\]](zc-rvaluecast-enforce-type-conversion-rules.md)|Принудительное применение правил преобразования явного типа Standard C++ (отключено по умолчанию).|
|[sizedDealloc\[-\]](zc-sizeddealloc-enable-global-sized-dealloc-functions.md)|Включить C ++ 14 глобальных размерных функций (на по умолчанию).|
|[strictStrings\[-\]](zc-strictstrings-disable-string-literal-type-conversion.md)|Отключение строкового литерала в `char*` или `wchar_t*` преобразования (отключено по умолчанию).|
|[троичный\[-\]](zc-ternary.md)|Принудительное применение правил условного оператора на типы операндов (отключено по умолчанию).|
|[threadSafeInit\[-\]](zc-threadsafeinit-thread-safe-local-static-initialization.md)|Включение потокобезопасной локальной статичной инициализации (на по умолчанию).|
|[throwingNew\[-\]](zc-throwingnew-assume-operator-new-throws.md)|Предположим, `operator new` вызывается при сбое (отключено по умолчанию).|
|[Триграфов\[-\]](zc-trigraphs-trigraphs-substitution.md)|Включите триграфы (устаревший, из системы по умолчанию).|
|[twoPhase-](zc-twophase.md)|Используйте шаблон, не соответствующий требованиям, синтаксический разбор (соответствие по умолчанию).|
|[wchar_t\[-\]](zc-wchar-t-wchar-t-is-native-type.md)|`wchar_t` является машинным типом, не является определением типа (на по умолчанию).|

Дополнительные сведения о вопросах соответствия в Visual C++ см. в статье [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).

## <a name="see-also"></a>См. также

[Параметры компилятора](compiler-options.md)<br/>
[Настройка параметров компилятора](setting-compiler-options.md)
