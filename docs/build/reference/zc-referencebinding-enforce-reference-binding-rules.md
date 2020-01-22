---
title: /Zc:referenceBinding (принудительное применение правил привязки ссылок)
ms.date: 03/06/2018
f1_keywords:
- referenceBinding
- /Zc:referenceBinding
helpviewer_keywords:
- -Zc compiler options (C++)
- referenceBinding
- Enforce reference binding rules
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 0c6cfaac-9c2a-41a3-aa94-64ca8ef261fc
ms.openlocfilehash: b7e297d6fd913ddda4d44a42298a361e314af0b5
ms.sourcegitcommit: a930a9b47bd95599265d6ba83bb87e46ae748949
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2020
ms.locfileid: "76518482"
---
# <a name="zcreferencebinding-enforce-reference-binding-rules"></a>/Zc:referenceBinding (принудительное применение правил привязки ссылок)

Если указан параметр **/Zc: referenceBinding** , компилятор не разрешает привязку неконстантной ссылки lvalue к временной.

## <a name="syntax"></a>Синтаксис

> **/Zc: referenceBinding**[ **-** ]

## <a name="remarks"></a>Заметки

Если указан параметр **/Zc: referenceBinding** , компилятор следует разделу 8.5.3 стандарта c++ 11: он не позволяет использовать выражения, связывающие определяемый пользователем тип с неконстантной ссылкой lvalue. По умолчанию или, если указан параметр **/Zc: referenceBinding-** , компилятор допускает такие выражения как расширение Майкрософт, но выдается предупреждение уровня 4. Для обеспечения безопасности, переносимости и соответствия кода рекомендуется использовать **/Zc: referenceBinding**.

Параметр **/Zc: referenceBinding** по умолчанию отключен. Параметр компилятора [/permissive-](permissive-standards-conformance.md) неявно задает этот параметр, но его можно переопределить с помощью параметра **/Zc: referenceBinding-** .

## <a name="example"></a>Пример

В этом примере показано расширение Microsoft, которое позволяет привязать временный тип определяемого пользователем типа к неконстантной ссылке lvalue.

```cpp
// zcreferencebinding.cpp
struct S {
};

void f(S&) {
}

S g() {
    return S{};
}

int main() {
    S& s = g();         // warning C4239 at /W4
    const S& cs = g();  // okay, bound to const ref
    f(g());             // Extension: error C2664 only if /Zc:referenceBinding
}
```

Дополнительные сведения о вопросах соответствия в Visual C++ см. в статье [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Перейдите на страницу свойств **Свойства конфигурации** > **C/C++**  > **Командная строка**.

1. Измените свойство **Дополнительные параметры** , включив параметр **/Zc: referenceBinding** , а затем нажмите кнопку **ОК**.

## <a name="see-also"></a>См. также:

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)<br/>
[/Zc (соответствие)](zc-conformance.md)<br/>
