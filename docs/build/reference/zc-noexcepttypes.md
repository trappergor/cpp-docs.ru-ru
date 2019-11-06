---
title: /Zc:noexceptTypes (правила noexcept C++17)
ms.date: 11/14/2017
f1_keywords:
- /Zc:noexceptTypes
helpviewer_keywords:
- /Zc:noexceptTypes
- Zc:noexceptTypes
- -Zc:noexceptTypes
ms.assetid: 1cbf7e3c-0f82-4f91-84dd-612bcf26d2c6
ms.openlocfilehash: 35bea7c2c629c615c60a6136f289b6b11926c054
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2019
ms.locfileid: "73624867"
---
# <a name="zcnoexcepttypes-c17-noexcept-rules"></a>/Zc:noexceptTypes (правила noexcept C++17)

Стандарт C++ 17 создает `throw()` псевдоним для `noexcept`, удаляет `throw(<type list>)` и `throw(...)`, а также позволяет включать `noexcept`в определенные типы. Это изменение может вызвать ряд проблем совместимости с исходным кодом в коде, который соответствует C++ 14 или более ранней версии. Параметр **/Zc: noexceptTypes** указывает соответствие стандарту c++ 17. **/Zc: noexceptTypes —** разрешает поведение c++ 14 и более ранних версий при компиляции кода в режиме c++ 17.

## <a name="syntax"></a>Синтаксис

> **/Zc: noexceptTypes**[-]

## <a name="remarks"></a>Заметки

Если указан параметр **/Zc: noexceptTypes** , компилятор соответствует стандарту c++ 17 и обрабатывает [Throw ()](../../cpp/exception-specifications-throw-cpp.md) в качестве псевдонима для [except](../../cpp/noexcept-cpp.md), удаляя `throw(<type list>)` и `throw(...)`, а также позволяет определенным типам включать `noexcept`. Параметр **/Zc: noexceptTypes** доступен только в том случае, если включена функция [/std: c++ 17](std-specify-language-standard-version.md) или [/std: Latest](std-specify-language-standard-version.md) . **/Zc: noexceptTypes** по умолчанию включен в соответствие стандарту ISO c++ 17. Параметр [/permissive-](permissive-standards-conformance.md) не влияет на **/Zc: noexceptTypes**. Отключите этот параметр, указав **/Zc: noexceptTypes-** to, чтобы вернуться к поведению c++ 14 `noexcept` при указании **/std: c++ 17** или **/std: Latest** .

Начиная с Visual Studio 2017 версии 15,5 C++ компилятор выполняет диагностику более несоответствий спецификаций исключений в объявлениях в режиме c++ 17 или при указании параметра [/permissive-](permissive-standards-conformance.md) .

В этом примере показано поведение объявлений с описателем исключения при установке или отключении параметра **/Zc: noexceptTypes** . Чтобы отобразить поведение при установке, Скомпилируйте с помощью `cl /EHsc /W4 noexceptTypes.cpp`. Чтобы отобразить поведение при отключении, Скомпилируйте с помощью `cl /EHsc /W4 /Zc:noexceptTypes- noexceptTypes.cpp`.

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

При компиляции с использованием параметра **/Zc: noexceptTypes**по умолчанию в примере создаются указанные предупреждения. Чтобы обновить код, используйте следующую команду:

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

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Перейдите на страницу свойств **Свойства конфигурации** > **C/C++**  > **Командная строка**.

1. Измените свойство **Дополнительные параметры** , чтобы включить **/Zc: noexceptTypes** или **/Zc: NoexceptTypes-** и нажмите кнопку **ОК**.

## <a name="see-also"></a>См. также

[/Zc (соответствие)](zc-conformance.md)\
[кроме](../../cpp/noexcept-cpp.md)\
[Спецификации исключений (throw)](../../cpp/exception-specifications-throw-cpp.md)
