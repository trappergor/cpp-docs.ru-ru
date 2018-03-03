---
title: "/Zc:ternary (принудительное применение правил условный оператор) | Документы Microsoft"
ms.date: 1/12/2018
ms.technology:
- cpp-tools
ms.topic: article
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
manager: ghogen
ms.openlocfilehash: c2c4f4e17d3cf72284ec68cf10e75824722d5440
ms.sourcegitcommit: ef2a263e193410782c6dfe47d00764263439537c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="zcternary-enforce-conditional-operator-rules"></a>/Zc:ternary (принудительное применение правил условный оператор)

Включите применение правил стандарта C++ для типов и const или volatile (cv) уточнения второго и третьего операнда в выражении условного оператора.

## <a name="syntax"></a>Синтаксис

> **/Zc:ternary**[**-**]

## <a name="remarks"></a>Примечания

Visual Studio версии 15,3 включает поддержку компилятора для C++ Стандартная условного (или троичный) оператор (**?:**) поведение. Стандарт C++ требует операндов того же типа и cv квалификаторов, или только один операнд однозначно преобразовываться в один и тот же тип и cv квалификации, что и другой, либо один или оба операнда быть выражение throw. В версиях до Visual Studio версии 15,5 компилятор разрешил преобразования, которые в стандарте неоднозначны. Когда **/Zc:ternary** параметр указан, компилятор соответствует стандарту и отклоняет код, который не удовлетворяет правилам для соответствующих типов и cv квалификации второго и третьего операндов.

**/Zc:ternary** параметр выключен по умолчанию. Используйте **/Zc:ternary** для включения поведения, соответствующие требованиям, или **/Zc:ternary-** для явного указания прежнее поведение компилятора несоответствующих. [/ Разрешительным-](permissive-standards-conformance.md) позволяет **/Zc:ternary**. 

### <a name="examples"></a>Примеры

В этом примере показано, как класс, предоставляющий обоих неявную инициализации из типа и преобразование в тип может привести к неоднозначные преобразования. Этот код, компилятор принимает по умолчанию, но отклонены, если **/Zc:ternary** или **/ разрешительным-** указано.

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

Требуется исправление заключается в том, вносить явное приведение предпочтительный общий тип, либо в одном направлении преобразование из участия в поиска компилятора для соответствия типов выполняя преобразование явно.

Этот распространенный шаблон важные исключением является тип операнда является одним из типов, идентифицирующий, таких как `const char*`, `const char16_t*`, и т. д. Это также можно воспроизвести с типы массивов и типов указателей, которые они decay для. Поведение при фактических второй или третий операнд?: зависит от строковый литерал типа соответствующий языковой стандарт используется. C ++ 17 был изменен семантику для этого случая с C ++ 14. В результате код в следующем примере принимается под **/std: c ++ 14** (компилятор по умолчанию), но он отклонены, если **/std: c ++ 17** указано.

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

В разделе **/Zc:ternary**, условные операторы отклоняет компилятора, где один из аргументов имеет тип void и другой — нет выражение throw. Обычно эти используется в стиле ASSERT макросы:

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

Обычным решением является просто заменить void() аргумент отличным от void.

В этом примере показан код, который создает ошибку при обоих **/Zc:ternary** и **/Zc:ternary-**:

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

Этот код ранее было присвоено этой ошибки:

```Output
error C2446: ':': no conversion from 'foo::<lambda_f6cd18702c42f6cd636bfee362b37033>' to 'foo::<lambda_717fca3fc65510deea10bc47e2b06be4>'
note: No user-defined-conversion operator available that can perform this conversion, or the operator cannot be called
```

С **/Zc:ternary** причину сбоя яснее; для архитектур, где любой из нескольких определяемого реализацией соглашения о вызовах может использоваться для создания каждого лямбда-выражения, компилятор выражает нет предпочтения может устранить неоднозначность подписи возможных лямбда-выражения. Новые выходные данные выглядят следующим образом:

```Output
error C2593: 'operator ?' is ambiguous
note: could be 'built-in C++ operator?(bool (__cdecl *)(int,int), bool (__cdecl *)(int,int))'
note: or       'built-in C++ operator?(bool (__stdcall *)(int,int), bool (__stdcall *)(int,int))'
note: or       'built-in C++ operator?(bool (__fastcall *)(int,int), bool (__fastcall *)(int,int))'
note: or       'built-in C++ operator?(bool (__vectorcall *)(int,int), bool (__vectorcall *)(int,int))'
note: while trying to match the argument list '(foo::<lambda_717fca3fc65510deea10bc47e2b06be4>, foo::<lambda_f6cd18702c42f6cd636bfee362b37033>)'
```

Типичной причиной возникновения проблемы, относящиеся к внедрению **/Zc:ternary** поставляется с использованием условного оператора в шаблоне метапрограммирования, как некоторые типы результата изменять в соответствии с этого параметра. В следующем примере показано два случая где **/Zc:ternary** изменяет тип результата условного выражения в контексте meta программирования:

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

Обычно разрешения в таких случаях заключается в применении `std::remove_reference` признака результат типа там, где необходимо для сохранения старого поведения.

Дополнительные сведения о вопросах соответствия в Visual C++ см. в статье [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **C/C++** > **командной строки** страницу свойств.

1. Изменить **Дополнительные параметры** включив **/Zc:ternary** или **/Zc:ternary-** и выберите **ОК**.

## <a name="see-also"></a>См. также

[/Zc (соответствие)](../../build/reference/zc-conformance.md)  
