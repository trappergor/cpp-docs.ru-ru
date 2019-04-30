---
title: /Zc:strictStrings (отключение преобразования типов строковых литералов)
ms.date: 03/06/2018
f1_keywords:
- /Zc:strictStrings
- strictStrings
helpviewer_keywords:
- /Zc:strictStrings
- -Zc compiler options (C++)
- strictStrings
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: b7eb3f3b-82c1-48a2-8e63-66bad7397b46
ms.openlocfilehash: 954088955a3f1530bb298aadbc35c7dd74150b7a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62315668"
---
# <a name="zcstrictstrings-disable-string-literal-type-conversion"></a>/Zc:strictStrings (отключение преобразования типов строковых литералов)

Если этот параметр указан, компилятор требует строгого соответствия `const`-квалификации для указателей, инициализированных с помощью строковых литералов.

## <a name="syntax"></a>Синтаксис

> **/Zc:strictStrings**[**-**]

## <a name="remarks"></a>Примечания

Если **/Zc: strictstrings** указан, компилятор применяет стандартного C++ `const` квалификации для строковых литералов, как тип "массив `const char`" или "массив `const wchar_t`", в зависимости от объявления. Строковые литералы являются неизменяемыми, и при попытке изменения содержимого одного из них возникает ошибка нарушения доступа во время выполнения. Необходимо объявить указатель на строку как указатель `const`, чтобы инициализировать его с помощью строкового литерала, или использовать явное приведение `const_cast` для инициализации указателя, не являющегося указателем `const`. По умолчанию или если **/Zc:strictStrings-** указан, компилятор не выполняет стандартного C++ `const` квалификации для указателей на строки, инициализируются с помощью строковых литералов.

**/Zc: strictstrings** параметр отключен по умолчанию. [/ Permissive-](permissive-standards-conformance.md) параметр компилятора неявно задает этот параметр, но его можно переопределить с помощью **/Zc:strictStrings-**.

Используйте **/Zc: strictstrings** параметр, чтобы предотвратить компиляцию неверного кода. В этом примере демонстрируется, как простая ошибка объявления приводит к сбою во время выполнения.

```cpp
// strictStrings_off.cpp
// compile by using: cl /W4 strictStrings_off.cpp
int main() {
   wchar_t* str = L"hello";
   str[2] = L'a'; // run-time error: access violation
}
```

Когда **/Zc: strictstrings** — включена, и тот же код сообщает об ошибке в объявлении `str`.

```cpp
// strictStrings_on.cpp
// compile by using: cl /Zc:strictStrings /W4 strictStrings_on.cpp
int main() {
   wchar_t* str = L"hello"; // error: Conversion from string literal
   // loses const qualifier
   str[2] = L'a';
}
```

При использовании `auto` для объявления указателя на строку компилятор автоматически создает правильное объявление типа указателя `const`. О попытке изменить содержимое указателя `const` компилятор сообщает как об ошибке.

> [!NOTE]
> Стандартная библиотека C++ в Visual Studio 2013 не поддерживает **/Zc: strictstrings** параметр компилятора в отладочной сборки. Если вы видите несколько [C2665](../../error-messages/compiler-errors-2/compiler-error-c2665.md) выход ошибок в построениях, это может быть причиной.

Дополнительные сведения о вопросах соответствия в Visual C++ см. в статье [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **C/C++** > **командной строки** страницу свойств.

1. Изменить **Дополнительные параметры** свойство **/Zc: strictstrings** и выберите **ОК**.

## <a name="see-also"></a>См. также

[/Zc (соответствие)](zc-conformance.md)<br/>
