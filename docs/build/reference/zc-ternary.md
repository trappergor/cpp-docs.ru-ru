---
title: /Zc:ternary (принудительное применение правил для условного оператора)
ms.date: 09/12/2019
f1_keywords:
- /Zc:ternary
helpviewer_keywords:
- /Zc:ternary
- Zc:ternary
- -Zc:ternary
ms.openlocfilehash: 7c95f061e195ccf7fef8a6a21d193b257baa5f39
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81335680"
---
# <a name="zcternary-enforce-conditional-operator-rules"></a>/Zc:ternary (принудительное применение правил для условного оператора)

Позволяет обеспечить соблюдение стандартных правил СЗ для типов и конст или нестабильной (cv) квалификации второго и третьего operands в условном выражении оператора.

## <a name="syntax"></a>Синтаксис

> **/Кк:тернари****-**

## <a name="remarks"></a>Remarks

Начиная с Visual Studio 2017, компилятор поддерживает стандартное *условное поведение* оператора СЗ **(?:**) поведение. Он также известен как *ternary оператора*. Стандарт СЗ требует, чтобы тернази и кв-квалификации удовлетворяли одно из трех условий: работы должны быть того же типа **и** нестабильной или **неустойчивой** квалификации (cv-квалификация), или только одна операндр должна быть однозначно конвертируемой к тому же типу и cv-квалификации, как и другие. Или, один или оба operands должны быть выражением броска. В версиях перед Visual Studio 2017 версии 15.5, компилятор допустил преобразования, которые считаются неоднозначными по стандарту.

При указании **опции /C:ternary** компилятор соответствует стандарту. Он отвергает код, который не соответствует правилам для соответствующих типов и cv-квалификации второго и третьего operands.

**Опция /C:ternary** отключена по умолчанию в Visual Studio 2017. Используйте **/C:ternary,** чтобы соответствовать поведению, или **/C:ternary-для** явного указания предыдущего несоответствия поведения компилятора. [/разрешительно-опция](permissive-standards-conformance.md) неявно позволяет эту опцию, но она может быть отменена с помощью **/ Кк: ternary-**.

### <a name="examples"></a>Примеры

Этот пример показывает, как класс, обеспечивающий как неявную инициализацию от типа, так и преобразование в тип, может привести к неоднозначным преобразованиям. Этот код принимается компилятором по умолчанию, но отклоняется, когда указано **/ Cc:ternary** или **/permissive-** .

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

Чтобы исправить этот код, сделайте явный отлитый для предпочтительного общего типа или предотвратите одно направление преобразования типа. Можно удержать компилятор от сопоставления преобразования типа, сделав преобразование явным.

Важным исключением из этого общего шаблона является, когда тип операнд является одним из `const char*` `const char16_t*`типов строк с нулевым завершением, таким как , и так далее. Вы также можете воспроизвести эффект с типами массивов и типами указателей, к которые они распадаются. Поведение, когда фактическая вторая или `?:` третья работа является строкой буквального соответствующего типа, зависит от используемого языкового стандарта. Для этого случая семантика c-17 изменилась семантика с C-14. В результате компилятор принимает код в следующем примере по умолчанию **/std:c'14,** но отклоняет его, когда вы указываете **/std:c'17**.

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

Чтобы исправить этот код, отбросьте один из operands явно.

В соответствии с **/C:ternary**, компилятор отвергает условных операторов, где один из аргументов имеет **пустоту**типа, а другой не является выражением броска. Общее использование этого шаблона в assert-подобных макросов:

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

Типичным решением является замена непустого аргумента `void()`.

В этом примере показан код, который генерирует ошибку в обоих **/ C: ternary** и **/ C: ternary-**:

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

Этот код ранее дал эту ошибку:

```Output
error C2446: ':': no conversion from 'foo::<lambda_f6cd18702c42f6cd636bfee362b37033>' to 'foo::<lambda_717fca3fc65510deea10bc47e2b06be4>'
note: No user-defined-conversion operator available that can perform this conversion, or the operator cannot be called
```

С **/Кк:тернари,** причина отказа становится яснее. Для генерации каждой лямбды можно использовать любые из нескольких конвенций вызова, определяемых реализацией. Тем не менее, компилятор не имеет правила предпочтения для disambiguate возможных подписей лямбда. Новый выход выглядит следующим образом:

```Output
error C2593: 'operator ?' is ambiguous
note: could be 'built-in C++ operator?(bool (__cdecl *)(int,int), bool (__cdecl *)(int,int))'
note: or       'built-in C++ operator?(bool (__stdcall *)(int,int), bool (__stdcall *)(int,int))'
note: or       'built-in C++ operator?(bool (__fastcall *)(int,int), bool (__fastcall *)(int,int))'
note: or       'built-in C++ operator?(bool (__vectorcall *)(int,int), bool (__vectorcall *)(int,int))'
note: while trying to match the argument list '(foo::<lambda_717fca3fc65510deea10bc47e2b06be4>, foo::<lambda_f6cd18702c42f6cd636bfee362b37033>)'
```

Общий источник проблем, найденных **в /C:ternary** исходит от условных операторов, используемых в мета-программировании шаблонов. Некоторые типы результатов изменяются под этим коммутатором. Следующий пример демонстрирует два случая, когда **/C:ternary** изменяет тип результата условного выражения в контексте, не отвечаемом у программирования:

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

Типичным исправлением `std::remove_reference` является применение черты на типе результата, где это необходимо для сохранения старого поведения.

Дополнительные сведения о вопросах соответствия в Visual C++ см. в статье [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите страницу свойства **командной** > **строки** Configuration Properties**C/C'.** > 

1. Измените свойство **дополнительных опций,** чтобы включить **/C:ternary** или **/c:ternary-** и затем выберите **OK.**

## <a name="see-also"></a>См. также раздел

[/Zc (соответствие)](zc-conformance.md)
