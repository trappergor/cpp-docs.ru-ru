---
title: "-Zc: noexceptTypes (C ++ 17 noexcept правила) | Документы Microsoft"
ms.date: 11/14/2017
ms.technology:
- cpp-tools
ms.topic: article
f1_keywords:
- /Zc:noexceptTypes
dev_langs:
- C++
helpviewer_keywords:
- /Zc:noexceptTypes
- Zc:noexceptTypes
- -Zc:noexceptTypes
ms.assetid: 1cbf7e3c-0f82-4f91-84dd-612bcf26d2c6
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: af455b9a781295f3e6f446b7dc5c3d253fe2f4c5
ms.sourcegitcommit: eeb2b5ad8d3d22514a7b9bd7d756511b69ae0ccf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2018
---
# <a name="zcnoexcepttypes-c17-noexcept-rules"></a>/Zc:noexceptTypes (c ++ 17 noexcept правила)

Делает стандарт C ++ 17 `throw()` в качестве псевдонима для `noexcept`, удаляет `throw(<type list>)` и `throw(...)`и позволяет включить определенные типы `noexcept`. Это может вызвать ряд проблем совместимости источника в коде, который соответствует до C ++ 14 или более ранней версии. **/Zc:noexceptTypes** параметр можно задать соответствие стандарт C ++ 17 или разрешать C ++ 14 и более ранних версиях поведение при компиляции кода в C ++ 17 режиме.

## <a name="syntax"></a>Синтаксис

> **/Zc:noexceptTypes**[-]

## <a name="remarks"></a>Примечания

Когда **/Zc:noexceptTypes** параметр указан, компилятор соответствует стандарт C ++ 17 и рассматривает [throw()](../../cpp/exception-specifications-throw-cpp.md) в качестве псевдонима для [noexcept](../../cpp/noexcept-cpp.md), удаляет `throw(<type list>)`и `throw(...)`и позволяет включить определенные типы `noexcept`. **/Zc:noexceptTypes** параметр доступен только тогда, когда [/std: c ++ 17](std-specify-language-standard-version.md) или [/std:latest](std-specify-language-standard-version.md) включен. **/Zc:noexceptTypes** включена по умолчанию в соответствии с ISO стандарт C ++ 17. [/ Разрешительным-](permissive-standards-conformance.md) параметр не влияет на **/Zc:noexceptTypes**. Отключить этот параметр, указав **/Zc:noexceptTypes-** вернуться к C ++ 14 поведение `noexcept` при **/std::C ++ 17** или **/std::latest** указано.

Начиная с версии 15,5 2017 г. Visual Studio, компилятор C++ проверяет дополнительные спецификации несоответствующие исключений в объявлениях в C ++ 17 режиме или когда [/ разрешительным-](permissive-standards-conformance.md) параметра.

В этом примере показано, как вести объявления со спецификатором исключения, когда **/Zc:noexceptTypes** задан или отключен параметр. Для демонстрации поведения при установке, компиляция с помощью `cl /EHsc /W4 noexceptTypes.cpp`. Для демонстрации поведения при отключении, компиляция с помощью `cl /EHsc /W4 /Zc:noexceptTypes- noexceptTypes.cpp`.

```cpp
// noexceptTypes.cpp
// Compile by using: cl /EHsc /W4 noexceptTypes.cpp
// Compile by using: cl /EHsc /W4 /Zc:noexceptTypes- noexceptTypes.cpp

void f() throw();    // equivalent to void f() noexcept;
void f() { }         // warning C5043
void g() throw(...); // warning C5040

struct A
{
    virtual void f() throw();
};

struct B : A
{
    virtual void f() { } // error C2694
};
```

При компиляции с параметром по умолчанию **/Zc:noexceptTypes**, пример приводит к возникновению указанных предупреждений. Чтобы обновить код, используйте следующую команду:

```cpp
void f() noexcept;
void f() noexcept { }
void g() noexcept(false);

struct A
{
    virtual void f() noexcept;
};

struct B : A
{
    virtual void f() noexcept { }
};
```

Дополнительные сведения о вопросах соответствия в Visual C++ см. в статье [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **C/C++** > **командной строки** страницу свойств.

1. Изменить **Дополнительные параметры** включив **/Zc:noexceptTypes** или **/Zc:noexceptTypes-** и выберите **ОК**.

## <a name="see-also"></a>См. также

[/Zc (соответствие)](../../build/reference/zc-conformance.md)  
[noexcept](../../cpp/noexcept-cpp.md)  
[Спецификации исключений (throw)](../../cpp/exception-specifications-throw-cpp.md)  
