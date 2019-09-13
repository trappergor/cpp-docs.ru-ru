---
title: /Zc:ternary (принудительное применение правил для условного оператора)
ms.date: 09/12/2019
f1_keywords:
- /Zc:ternary
helpviewer_keywords:
- /Zc:ternary
- Zc:ternary
- -Zc:ternary
ms.openlocfilehash: 5c38a09b92b4173ca962412a413abc283db590ff
ms.sourcegitcommit: effb516760c0f956c6308eeded48851accc96b92
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70927495"
---
# <a name="zcternary-enforce-conditional-operator-rules"></a>/Zc:ternary (принудительное применение правил для условного оператора)

Включите применение C++ стандартных правил для типов, а также квалификаторов const или volatile (ОПС) второго и третьего операндов в выражении условного оператора.

## <a name="syntax"></a>Синтаксис

> **/Zc: ternary** [ **-** ]

## <a name="remarks"></a>Примечания

Начиная с Visual Studio 2017, компилятор поддерживает C++ стандартное поведение *условного оператора* ( **?:** ). Он также называется *оператором ternary*. Стандарт C++ требует, чтобы операнды ternary удовлетворяли одному из трех условий: Операнды должны иметь один и тот же тип, а также **квалификаторы Const** или **volatile** (ОПС-квалификация) или только один операнд должен однозначно преобразовываться в один и тот же тип, а ОПС-квалификация — в качестве другого. Или один или оба операнда должны быть выражением Throw. В версиях до Visual Studio 2017 версии 15,5 компилятор разрешил преобразования, которые считаются неоднозначными по стандарту.

Если указан параметр **/Zc: ternary** , компилятор соответствует стандарту. Он отклоняет код, который не удовлетворяет правилам для сопоставленных типов, и уточнения ОПС второго и третьего операндов.

По умолчанию в Visual Studio 2017 параметр **/Zc: ternary** отключен. Используйте **/Zc: ternary** , чтобы включить поведение при согласовании, или **/Zc: ternary —** для явного указания предыдущего не согласованного поведения компилятора. Параметр [/permissive-](permissive-standards-conformance.md) неявно включает этот параметр, но его можно переопределить с помощью параметра **/Zc: ternary-** .

### <a name="examples"></a>Примеры

В этом примере показано, как класс, который предоставляет неявную инициализацию из типа и преобразование в тип, может привести к неоднозначному преобразованию. Этот код принимается компилятором по умолчанию, но отклоняется, если указан параметр **/Zc: ternary** или **/permissive-** .

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

Чтобы исправить этот код, выполните явное приведение к предпочтительному общему типу или запретите преобразование типа в одном направлении. Можно запретить компилятору сопоставлять преобразования типов, делая преобразование явным.

Важным исключением из этого общего шаблона является то, что тип операндов является одним из строковых типов, завершающихся нулем, таких как `const char*`, `const char16_t*`и т. д. Кроме того, можно воспроизвести результат с типами массивов и типами указателей, в которые они Decay. Поведение, когда фактический второй или третий операнд в `?:` является строковым литералом соответствующего типа, зависит от используемого стандарта языка. В c++ 17 была изменена семантика для этого случая с C++ 14. В результате компилятор принимает код, приведенный в следующем примере, в/std по умолчанию **: c++ 14**, но отклоняет его при указании **/std: c++ 17**.

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

Чтобы исправить этот код, явно приведите один из операндов.

В разделе **/Zc: ternary**компилятор отклоняет условные операторы, где один из аргументов имеет тип **void**, а другой не является выражением Throw. Обычно этот шаблон используется в макросах, похожих на УТВЕРЖДЕНные:

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

Типичным решением является замена аргумента `void()`, отличного от void, на.

В этом примере показан код, который создает ошибку в параметрах **/Zc: ternary** и **/Zc: ternary-** :

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

Этот код ранее предоставил эту ошибку:

```Output
error C2446: ':': no conversion from 'foo::<lambda_f6cd18702c42f6cd636bfee362b37033>' to 'foo::<lambda_717fca3fc65510deea10bc47e2b06be4>'
note: No user-defined-conversion operator available that can perform this conversion, or the operator cannot be called
```

При использовании **/Zc: ternary**причина сбоя превращается в более четкий. Для создания каждого лямбда-выражения можно использовать любое из нескольких соглашений о вызовах, определенных реализацией. Однако у компилятора нет правила предпочтений для устранения неоднозначности возможных лямбда-подписей. Новые выходные данные выглядят следующим образом:

```Output
error C2593: 'operator ?' is ambiguous
note: could be 'built-in C++ operator?(bool (__cdecl *)(int,int), bool (__cdecl *)(int,int))'
note: or       'built-in C++ operator?(bool (__stdcall *)(int,int), bool (__stdcall *)(int,int))'
note: or       'built-in C++ operator?(bool (__fastcall *)(int,int), bool (__fastcall *)(int,int))'
note: or       'built-in C++ operator?(bool (__vectorcall *)(int,int), bool (__vectorcall *)(int,int))'
note: while trying to match the argument list '(foo::<lambda_717fca3fc65510deea10bc47e2b06be4>, foo::<lambda_f6cd18702c42f6cd636bfee362b37033>)'
```

Распространенный источник проблем, обнаруженных параметром **/Zc: ternary** , поступает из условных операторов, используемых в мета-программировании шаблона. Некоторые типы результатов изменяются в этом параметре. В следующем примере показаны два случая, в которых параметр **/Zc: ternary** изменяет тип результата условного выражения в контексте Немета-программирования:

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

Типичным исправлением является применение признаков `std::remove_reference` к типу результата, где необходимо сохранить старое поведение.

Дополнительные сведения о вопросах соответствия в Visual C++ см. в статье [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Перейдите на страницу свойств **Свойства конфигурации** > **C/C++**  > **Командная строка**.

1. Измените свойство **Дополнительные параметры** , чтобы включить **/Zc: ternary** или **/Zc: Ternary-** и нажмите кнопку **ОК**.

## <a name="see-also"></a>См. также

[/Zc (соответствие)](zc-conformance.md)
