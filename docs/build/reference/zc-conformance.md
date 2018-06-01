---
title: /Zc (соответствие) | Документы Microsoft
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
ms.openlocfilehash: b89744235a5a2302a6550b2ffa7100511ad2e59c
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704897"
---
# <a name="zc-conformance"></a>/Zc (соответствие)

Можно использовать **/Zc** параметры компилятора для указания поведения стандартного или версию компилятора.

## <a name="syntax"></a>Синтаксис

> **/ Zc:**_параметр_{,_параметр_}

## <a name="remarks"></a>Примечания

При реализации расширения в C или C++, который не совместим со стандартом Visual Studio можно использовать `/Zc` соответствия параметр, чтобы указать поведение соответствующих standard или версию. Некоторые варианты поведения, связанного с Microsoft используется по умолчанию, для предотвращения крупномасштабных критических изменений в существующий код. В других случаях значение по умолчанию — стандартное поведение улучшения безопасности, производительности и совместимости, где перевешивают затраты критических изменений. Значение по умолчанию каждый параметр соответствие может измениться в более новых версиях Visual Studio. Дополнительные сведения о параметрах соответствия см. в разделе для конкретного параметра. [/ Разрешительным-](permissive-standards-conformance.md) параметр компилятора неявно задает параметры соответствия, не заданных по умолчанию для своего срока соответствует стандартам.

Это `/Zc` параметры компилятора:

|Параметр|Поведение|
|---|---|
|[alignedNew\[-\]](zc-alignednew.md)|Включить C ++ 17 чрезмерно выровненных динамическое выделение (включен по умолчанию в C ++ 17).|
|[Авто\[-\]](zc-auto-deduce-variable-type.md)|Применить новое значение стандартного C++ для `auto` (на по умолчанию).|
|[__cplusplus\[-\]](zc-cplusplus.md)|Включить **__cplusplus** макрос для отчета, поддерживается стандарт (отключено по умолчанию).|
|[externConstexpr\[-\]](zc-externconstexpr.md)|Включить внешнюю компоновку для `constexpr` переменных (отключено по умолчанию).|
|[forScope\[-\]](zc-forscope-force-conformance-in-for-loop-scope.md)|Обеспечить выполнение стандартным C++ `for` правила области видимости (на по умолчанию).|
|[implicitNoexcept\[-\]](zc-implicitnoexcept-implicit-exception-specifiers.md)|Включение неявного `noexcept` на требуемые функции (на по умолчанию).|
|[Встроенная\[-\]](zc-inline-remove-unreferenced-comdat.md)|Удалите неиспользуемые функции или данные, если она COMDAT или имеют только внутреннюю связь (отключено по умолчанию).|
|[noexceptTypes\[-\]](zc-noexcepttypes.md)|Принудительное применение C ++ 17 noexcept правил (на по умолчанию в C ++ 17 или более поздней версии).|
|[referenceBinding\[-\]](zc-referencebinding-enforce-reference-binding-rules.md)|Временный определяемого пользователем ТИПА не будет привязан к ссылки lvalue неконстантной (отключено по умолчанию).|
|[rvalueCast\[-\]](zc-rvaluecast-enforce-type-conversion-rules.md)|Принудительное применение правил преобразования явного типа Standard C++ (отключено по умолчанию).|
|[sizedDealloc\[-\]](zc-sizeddealloc-enable-global-sized-dealloc-functions.md)|Включить C ++ 14 глобальных размерных функциях удаления функций (на по умолчанию).|
|[strictStrings\[-\]](zc-strictstrings-disable-string-literal-type-conversion.md)|Строковый литерал, чтобы отключить `char*` или `wchar_t*` преобразования (отключено по умолчанию).|
|[троичный\[-\]](zc-ternary.md)|Принудительное применение правил условного оператора на типы операндов (отключено по умолчанию).|
|[threadSafeInit\[-\]](zc-threadsafeinit-thread-safe-local-static-initialization.md)|Включение потокобезопасной локальной статичной инициализации (на по умолчанию).|
|[throwingNew\[-\]](zc-throwingnew-assume-operator-new-throws.md)|Предположим, `operator new` сбое (отключено по умолчанию).|
|[триграфов\[-\]](zc-trigraphs-trigraphs-substitution.md)|Включите триграфы (устаревший, отключение по умолчанию).|
|[twoPhase-](zc-twophase.md)|Используйте шаблон, не соответствующих разбор (соответствующий по умолчанию).|
|[wchar_t\[-\]](zc-wchar-t-wchar-t-is-native-type.md)|`wchar_t` Это собственный тип не является определением типа (на по умолчанию).|

Дополнительные сведения о вопросах соответствия в Visual C++ см. в статье [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).

## <a name="see-also"></a>См. также

[Параметры компилятора](compiler-options.md)  
[Настройка параметров компилятора](setting-compiler-options.md)
