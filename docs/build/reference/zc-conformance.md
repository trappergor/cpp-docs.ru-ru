---
title: /Zc (соответствие)
ms.date: 03/06/2018
helpviewer_keywords:
- /Zc compiler options [C++]
- -Zc compiler options [C++]
- Conformance compiler options
- Zc compiler options [C++]
ms.assetid: db1cc175-6e93-4a2e-9396-c3725d2d8f71
ms.openlocfilehash: 4422524deab2a749c96d5e967bc3223d0c9c9873
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79438672"
---
# <a name="zc-conformance"></a>/Zc (соответствие)

Параметры компилятора **/Zc** можно использовать для указания стандартного или специфического поведения компилятора для конкретного приложения.

## <a name="syntax"></a>Синтаксис

> **/Zc:** _параметр_{,_параметр_}

## <a name="remarks"></a>Remarks

Когда Visual Studio реализовала расширение для C или C++ не совместимо со стандартом, можно использовать параметр соответствия `/Zc`, чтобы указать стандартное соответствие или поведение, специфическое для Microsoft. Для некоторых параметров поведение по умолчанию зависит от Майкрософт, чтобы предотвратить крупномасштабные критические изменения в существующем коде. В других случаях по умолчанию используется стандартное поведение, в котором улучшения безопасности, производительности или совместимости перевешивают затраты на критические изменения. Значение по умолчанию для каждого параметра соответствия может измениться в более новых версиях Visual Studio. Дополнительные сведения о каждом параметре соответствия см. в разделе, посвященном конкретному параметру. Параметр компилятора [/permissive-](permissive-standards-conformance.md) неявно задает параметры соответствия, которые по умолчанию не заданы в соответствии с установленным параметром соответствия.

Ниже приведены `/Zc` параметры компилятора.

|Параметр|Поведение|
|---|---|
|[alignedNew\[-\]](zc-alignednew.md)|Включить динамическое выделение в C++ 17 по рассогласованию (включено по умолчанию в C++ 17).|
|[Автоматическое\[-\]](zc-auto-deduce-variable-type.md)|Применить новое стандартное C++ значение для `auto` (включено по умолчанию).|
|[__cplusplus\[-\]](zc-cplusplus.md)|Включите макрос **__cplusplus** , чтобы сообщить о поддерживаемом стандарте (отключено по умолчанию).|
|[externConstexpr\[-\]](zc-externconstexpr.md)|Включите внешнюю компоновку для переменных `constexpr` (по умолчанию отключено).|
|[-\[forScope \]](zc-forscope-force-conformance-in-for-loop-scope.md)|Применять стандартные C++ правила `for` области (включено по умолчанию).|
|[implicitNoexcept\[-\]](zc-implicitnoexcept-implicit-exception-specifiers.md)|Включить неявные `noexcept` в обязательных функциях (по умолчанию включено).|
|[Встроенный\[-\]](zc-inline-remove-unreferenced-comdat.md)|Удалите неиспользуемую функцию или данные, если они имеют значение COMDAT или только внутренние компоновки (отключено по умолчанию).|
|[noexceptTypes\[-\]](zc-noexcepttypes.md)|Применить правила C++ 17, кроме правил (включено по умолчанию в C++ 17 или более поздней версии).|
|[referenceBinding\[-\]](zc-referencebinding-enforce-reference-binding-rules.md)|Временная операция определяемого пользователем типа не будет привязана к неконстантной ссылке lvalue (по умолчанию отключена).|
|[rvalueCast\[-\]](zc-rvaluecast-enforce-type-conversion-rules.md)|Применять стандартные C++ правила явного преобразования типов (по умолчанию отключены).|
|[sizedDealloc\[-\]](zc-sizeddealloc-enable-global-sized-dealloc-functions.md)|Включить глобальные функции выделения размера в C++ 14 (включено по умолчанию).|
|[strictStrings\[-\]](zc-strictstrings-disable-string-literal-type-conversion.md)|Отключите преобразование строкового литерала в `char*` или `wchar_t*` (отключено по умолчанию).|
|[ternary\[-\]](zc-ternary.md)|Применение правил условного оператора к типам операндов (по умолчанию отключено).|
|[threadSafeInit\[-\]](zc-threadsafeinit-thread-safe-local-static-initialization.md)|Включите потокобезопасную локальную статическую инициализацию (по умолчанию).|
|[throwingNew\[-\]](zc-throwingnew-assume-operator-new-throws.md)|Предполагается, что `operator new` создает исключение при сбое (отключено по умолчанию).|
|[триграфов\[-\]](zc-trigraphs-trigraphs-substitution.md)|Включить триграфов (устарело, по умолчанию отключено).|
|[twoPhase](zc-twophase.md)|Используйте несоответствие поведения синтаксического анализа шаблона (по умолчанию соответствует).|
|[wchar_t\[-\]](zc-wchar-t-wchar-t-is-native-type.md)|`wchar_t` является собственным типом, а не typedef (on по умолчанию).|

Дополнительные сведения о вопросах соответствия в Visual C++ см. в статье [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).

## <a name="see-also"></a>См. также раздел

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
