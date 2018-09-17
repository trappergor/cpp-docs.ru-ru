---
title: '/ Zc: ternary (принудительное применение правил условного оператора) | Документация Майкрософт'
ms.date: 3/06/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Zc:ternary
dev_langs:
- C++
helpviewer_keywords:
- /Zc:ternary
- Zc:ternary
- -Zc:ternary
author: corob-msft
ms.author: corob
ms.openlocfilehash: a8cd0a4034b07d170bc9ca531d60cce508681a2a
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45717827"
---
# <a name="zcternary-enforce-conditional-operator-rules"></a>/ Zc: ternary (принудительное применение правил условного оператора)

Включите применение правил стандарт C++ для типов и уточнения const или volatile (cv) второй и третий операнды в выражении условный оператор.

## <a name="syntax"></a>Синтаксис

> **/ Zc: ternary**[**-**]

## <a name="remarks"></a>Примечания

Visual Studio версии 15.3 включает поддержку компилятора для C++ standard условного (или троичный) оператор (**?:**) поведение. Стандарт C++ требует операндов одного типа и cv квалификации, или только один операнд должен быть однозначно можно преобразовать в один и тот же тип и cv квалификации, чем в другом, либо один или оба операнда выражением throw. В версиях до Visual Studio версии 15.5 компилятор разрешил преобразований, которые в стандарте неоднозначны. Когда **/Zc: ternary** параметр указан, компилятор соответствует стандарту и отклоняет код, который не удовлетворяет правилам для соответствующих типов и cv квалификации, второго и третьего операндов.

**/Zc: ternary** параметр отключен по умолчанию. Используйте **/Zc: ternary** для включения соответствующих поведения или **/Zc:ternary-** в явном виде прежнее поведение компилятора, не соответствующий требованиям. [/ Permissive-](permissive-standards-conformance.md) параметр неявно включает этот параметр, но его можно переопределить с помощью **/Zc:ternary-**.

### <a name="examples"></a>Примеры

В этом примере показано, как класс, предоставляющий обоих неявную инициализации из типа и преобразование в тип может привести к неоднозначные преобразования. Этот код принимает компилятор по умолчанию, но отклонены, если **/Zc: ternary** или **/ permissive-** указан.

```cpp
// zcternary1.cpp
// Compile by using: cl /EHsc /W4 /nologo /Zc:ternary zcternary1.cpp

struct A
{
   long l;
   A(int i) : l{i} {}    // explicit prevents conversion of int
   operator int() const { return static_cast<int>(l); }
};

int main()
{
   A a(42);
   // Accepted when /Zc:ternary (or /permissive-) is not used
   auto x = true ? 7 : a;  // old behavior prefers A(7) over (int)a
   auto y = true ? A(7) : a;   // always accepted
   auto z = true ? 7 : (int)a; // always accepted
   return x + y + z;
}
```

Требуется исправление является сделать явное приведение предпочтительный общий тип, либо в одном направлении преобразования из участия в поиска компилятора для соответствия типов, сделав явное преобразование.

Этот распространенный шаблон важное исключение — когда тип операндов один из типов заканчивающуюся нулем строку, такие как `const char*`, `const char16_t*`, и т. д. Это также можно воспроизвести с помощью типы массивов и типов указателей, которые они decay для. Поведение при фактическое второй или третий операнд?: имеет строковый литерал соответствующий тип зависит от стандартный язык, используемый. C ++ 17 изменилось семантику для этого случая с C ++ 14. Таким образом, код в следующем примере принимается в разделе **/std: c ++ 14** (компилятора по умолчанию), но является отклонены, если **/std: c ++ 17** указан.

```cpp
// zcternary2.cpp
// Compile by using: cl /EHsc /W4 /nologo /Zc:ternary /std:c++17 zcternary2.cpp

struct MyString
{
   const char * p;
   MyString(const char* s = "") noexcept : p{s} {} // from char*
   operator const char*() const noexcept { return p; } // to char*
};

int main()
{
   MyString s;
   auto x = true ? "A" : s; // MyString: permissive prefers MyString("A") over (const char*)s
}
```

Чтобы исправить этот код, один из операндов явное приведение.

В разделе **/Zc: ternary**, условные операторы отклоняет компилятора, где один из аргументов имеет тип void, и другой не является выражением throw. Обычно из них используется в макросах ASSERT по принципу:

```cpp
// zcternary3.cpp
// Compile by using: cl /EHsc /W4 /nologo /Zc:ternary /c zcternary3.cpp

void myassert(const char* text, const char* file, int line);
#define ASSERT(ex) (void)((ex) ? 0 : myassert(#ex, __FILE__, __LINE__))
// To fix, define it this way instead:
// #define ASSERT(ex) (void)((ex) ? void() : myassert(#ex, __FILE__, __LINE__))

int main()
{
   ASSERT(false);  // C3447
}
```

Обычным решением является просто замените аргумент отличный от void void().

В этом примере показан код, который создает ошибку при обоих **/Zc: ternary** и **/Zc:ternary-**:

```cpp
// zcternary4.cpp
// Compile by using:
//   cl /EHsc /W4 /nologo /Zc:ternary zcternary4.cpp
//   cl /EHsc /W4 /nologo /Zc:ternary zcternary4.cpp

int main() {
   auto p1 = [](int a, int b) { return a > b; };
   auto p2 = [](int a, int b) { return a > b; };
   auto p3 = true ? p1 : p2; // C2593 under /Zc:ternary, was C2446
}
```

Этот код присваивает ранее Эта ошибка:

```Output
error C2446: ':': no conversion from 'foo::<lambda_f6cd18702c42f6cd636bfee362b37033>' to 'foo::<lambda_717fca3fc65510deea10bc47e2b06be4>'
note: No user-defined-conversion operator available that can perform this conversion, or the operator cannot be called
```

С помощью **/Zc: ternary** причину сбоя становится понятнее; в архитектурах, где любой из нескольких определяемого реализацией соглашения о вызовах может использоваться для создания каждого лямбда-выражения, компилятор выражает не существует предпочтения между ними могут устранить неоднозначность подписи возможных лямбда-выражения. Новые выходные данные выглядит следующим образом:

```Output
error C2593: 'operator ?' is ambiguous
note: could be 'built-in C++ operator?(bool (__cdecl *)(int,int), bool (__cdecl *)(int,int))'
note: or       'built-in C++ operator?(bool (__stdcall *)(int,int), bool (__stdcall *)(int,int))'
note: or       'built-in C++ operator?(bool (__fastcall *)(int,int), bool (__fastcall *)(int,int))'
note: or       'built-in C++ operator?(bool (__vectorcall *)(int,int), bool (__vectorcall *)(int,int))'
note: while trying to match the argument list '(foo::<lambda_717fca3fc65510deea10bc47e2b06be4>, foo::<lambda_f6cd18702c42f6cd636bfee362b37033>)'
```

Распространенным источником проблем, связанных с внедрения **/Zc: ternary** поступает из использования условного оператора в шаблоне метапрограммирования, как изменить некоторые из типов результатов под этот переключатель. В следующем примере показано два случая где **/Zc: ternary** изменяет тип результата условного выражения в контексте meta программирования:

```cpp
// zcternary5.cpp
// Compile by using: cl /EHsc /W4 /nologo /Zc:ternary zcternary5.cpp

int main(int argc, char**) {
   char a = 'A';
   const char b = 'B';
   decltype(auto) x = true ? a : b; // char without, const char& with /Zc:ternary
   const char(&z)[2] = argc > 3 ? "A" : "B"; // const char* without /Zc:ternary
   return x > *z;
}
```

Типичный решение в таких случаях является применение `std::remove_reference` признака на результат введите, где они нужны, чтобы сохранить старое поведение.

Дополнительные сведения о вопросах соответствия в Visual C++ см. в статье [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **C/C++** > **командной строки** страницу свойств.

1. Изменить **Дополнительные параметры** свойство **/Zc: ternary** или **/Zc:ternary-** и выберите **ОК**.

## <a name="see-also"></a>См. также

[/Zc (соответствие)](../../build/reference/zc-conformance.md)
