---
title: "/Zc:referenceBinding (принудительное применение правил привязки ссылку) | Документы Microsoft"
ms.custom: 
ms.date: 03/06/2018
ms.technology:
- cpp-tools
ms.topic: article
f1_keywords:
- referenceBinding
- /Zc:referenceBinding
dev_langs:
- C++
helpviewer_keywords:
- -Zc compiler options (C++)
- referenceBinding
- Enforce reference binding rules
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 0c6cfaac-9c2a-41a3-aa94-64ca8ef261fc
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a8e3b10f5b2108a4c0e29d802951015749775a27
ms.sourcegitcommit: eeb2b5ad8d3d22514a7b9bd7d756511b69ae0ccf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2018
---
# <a name="zcreferencebinding-enforce-reference-binding-rules"></a>/Zc:referenceBinding (принудительное применение правил привязки ссылка)

Когда **/Zc:referenceBinding** параметр указан, компилятор не допускает ссылку lvalue неконстантной для привязки к временной.

## <a name="syntax"></a>Синтаксис

> **/Zc:referenceBinding**[**-**]

## <a name="remarks"></a>Примечания

Если **/Zc:referenceBinding** указан, компилятор следует разделу 8.5.3 C ++ 11 standard и не позволяет использовать выражения, привязывающие определяемого пользователем типа временных ссылки lvalue неконстантной. По умолчанию или если **/Zc:referenceBinding-** указан, компилятор разрешает таких выражений как расширение Microsoft, но выдается предупреждение уровня 4. Для безопасности кода, переносимость и соответствия, мы рекомендуем использовать **/Zc:referenceBinding**.

**/Zc:referenceBinding** параметр выключен по умолчанию. [/ Разрешительным-](permissive-standards-conformance.md) параметр компилятора неявно устанавливает этот параметр, но его можно переопределить с помощью **/Zc:referenceBinding-**.

## <a name="example"></a>Пример

В этом примере показано расширение Microsoft, которое обеспечивает временное определяемого пользователем типа может быть привязано к ссылку lvalue неконстантной.

```cpp
// zcreferencebinding.cpp
struct S {
};

void f(S&) {
}

S g() {
    return S{};
}

void main() {
    S& s = g();         // warning C4239 at /W4
    const S& cs = g();  // okay, bound to const ref
    f(g());             // Extension: error C2664 only if /Zc:referenceBinding
}
```

Дополнительные сведения о вопросах соответствия в Visual C++ см. в статье [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **C/C++** > **командной строки** страницу свойств.

1. Изменить **Дополнительные параметры** включив **/Zc:referenceBinding** и выберите **ОК**.

## <a name="see-also"></a>См. также

[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)<br/>
[/Zc (соответствие)](../../build/reference/zc-conformance.md)<br/>
