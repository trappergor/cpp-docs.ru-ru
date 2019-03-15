---
title: '/ Zc: noexcepttypes (правила c ++ 17 noexcept)'
ms.date: 11/14/2017
f1_keywords:
- /Zc:noexceptTypes
helpviewer_keywords:
- /Zc:noexceptTypes
- Zc:noexceptTypes
- -Zc:noexceptTypes
ms.assetid: 1cbf7e3c-0f82-4f91-84dd-612bcf26d2c6
ms.openlocfilehash: 28e06f54049d36262134b6be7eadb0e6e5349a45
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57812113"
---
# <a name="zcnoexcepttypes-c17-noexcept-rules"></a>/ Zc: noexcepttypes (правила c ++ 17 noexcept)

Стандарт C ++ 17 делает `throw()` в качестве псевдонима для `noexcept`, удаляет `throw(<type list>)` и `throw(...)`и позволяет включать определенные типы `noexcept`. Это может вызвать ряд проблем совместимости источника в коде, который соответствует C ++ 14 или более ранней версии. **/Zc: noexcepttypes** параметр можно указать соответствие стандарт C ++ 17 или разрешать C ++ 14 и более ранних версиях поведение при компиляции кода в режиме C ++ 17.

## <a name="syntax"></a>Синтаксис

> **/ Zc: noexcepttypes**[-]

## <a name="remarks"></a>Примечания

Когда **/Zc: noexcepttypes** параметр указан, компилятор соответствует стандарт C ++ 17 и рассматривает [throw()](../../cpp/exception-specifications-throw-cpp.md) в качестве псевдонима для [noexcept](../../cpp/noexcept-cpp.md), удаляет `throw(<type list>)`и `throw(...)`и позволяет включать определенные типы `noexcept`. **/Zc: noexcepttypes** параметр доступен только тогда, когда [/std: c ++ 17](std-specify-language-standard-version.md) или [/std:latest](std-specify-language-standard-version.md) включен. **/ Zc: noexcepttypes** включена по умолчанию в соответствии с ISO стандарт C ++ 17. [/ Permissive-](permissive-standards-conformance.md) параметр не влияет на **/Zc: noexcepttypes**. Отключить этот параметр, указав **/Zc:noexceptTypes-** для возврата к C ++ 14 поведение `noexcept` при **/std::C ++ 17** или **/std::latest** указан.

Начиная с Visual Studio 2017 версии 15.5, компилятор C++ проверяет дополнительные спецификации несоответствующих исключений в объявлениях в режиме C ++ 17 или когда [/ permissive-](permissive-standards-conformance.md) параметра.

В этом примере показано, как вести объявления с спецификатор исключения, когда **/Zc: noexcepttypes** задан или отключен параметр. Для демонстрации поведения при установке, компиляция с помощью `cl /EHsc /W4 noexceptTypes.cpp`. Для демонстрации поведения при отключении, компиляция с помощью `cl /EHsc /W4 /Zc:noexceptTypes- noexceptTypes.cpp`.

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

При компиляции с использованием параметров по умолчанию **/Zc: noexcepttypes**, пример формирует указанные предупреждения. Чтобы обновить код, используйте следующее:

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

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **C/C++** > **командной строки** страницу свойств.

1. Изменить **Дополнительные параметры** свойство **/Zc: noexcepttypes** или **/Zc:noexceptTypes-** и выберите **ОК**.

## <a name="see-also"></a>См. также

[/Zc (соответствие)](zc-conformance.md)<br/>
[noexcept](../../cpp/noexcept-cpp.md)<br/>
[Спецификации исключений (throw)](../../cpp/exception-specifications-throw-cpp.md)
