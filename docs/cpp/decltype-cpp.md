---
title: decltype (C++)
ms.date: 11/04/2016
f1_keywords:
- decltype_cpp
helpviewer_keywords:
- operators [C++], decltype
- decltype operator
- operators [C++], type of an expression
- operators [C++], deduce expression type
ms.assetid: 6dcf8888-8196-4f13-af50-51e3797255d4
ms.openlocfilehash: 1ed07b8987df7b621ea2809409069cc1121fa24f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180216"
---
# <a name="decltype--c"></a>decltype (C++)

Описатель типа **decltype** Возвращает тип указанного выражения. Описатель типа **decltype** вместе с [ключевым словом auto](../cpp/auto-cpp.md)полезен в основном для разработчиков, создающих библиотеки шаблонов. Используйте **Auto** и **decltype** для объявления функции шаблона, тип возвращаемого значения которого зависит от типов своих аргументов шаблона. Или используйте **Auto** и **decltype** для объявления функции-шаблона, которая создает оболочку для вызова другой функции, а затем возвращает тип возвращаемого значения функции с оболочкой.

## <a name="syntax"></a>Синтаксис

```
decltype( expression )
```

### <a name="parameters"></a>Параметры

|Параметр|Description|
|---------------|-----------------|
|*expression*|Выражение. Дополнительные сведения см. в разделе [выражения](../cpp/expressions-cpp.md).|

## <a name="return-value"></a>Возвращаемое значение

Тип параметра *выражения* .

## <a name="remarks"></a>Remarks

Описатель типа **decltype** поддерживается в Visual Studio 2010 или более поздних версиях и может использоваться с машинным или управляемым кодом. `decltype(auto)` (C++ 14) поддерживается в Visual Studio 2015 и более поздних версиях.

Для определения типа параметра *выражения* компилятор использует следующие правила.

- Если параметр *выражения* является идентификатором или [доступом к члену класса](../cpp/member-access-operators-dot-and.md), `decltype(expression)` является типом сущности с именем *Expression*. Если такая сущность или параметр *выражения* не называет набор перегруженных функций, компилятор выдает сообщение об ошибке.

- Если параметр *выражения* является вызовом функции или перегруженной функции оператора, `decltype(expression)` является типом возвращаемого значения функции. Скобки вокруг перегруженного оператора игнорируются.

- Если параметр *Expression* является [rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md), `decltype(expression)` является типом *выражения*. Если параметр *Expression* является [левосторонним](../cpp/lvalues-and-rvalues-visual-cpp.md)значением, `decltype(expression)` является [ссылкой lvalue](../cpp/lvalue-reference-declarator-amp.md) на тип *выражения*.

В следующем примере кода демонстрируется использование описателя типа **decltype** . Допустим, во-первых, что были закодированы следующие операторы.

```cpp
int var;
const int&& fx();
struct A { double x; }
const A* a = new A();
```

Затем проверьте типы, возвращаемые четырьмя инструкциями **decltype** в следующей таблице.

|.|Тип|Примечания|
|---------------|----------|-----------|
|`decltype(fx());`|`const int&&`|[Ссылка rvalue](../cpp/rvalue-reference-declarator-amp-amp.md) на **Константное целое**.|
|`decltype(var);`|**int**|Тип переменной `var`.|
|`decltype(a->x);`|**double**|Тип членского доступа.|
|`decltype((a->x));`|`const double&`|Внутренние скобки вызывают оценку оператора в качестве выражения, а не членского доступа. А поскольку `a` объявляется как указатель `const`, тип является ссылкой на **константу типа Double**.|

## <a name="decltype-and-auto"></a>Decltype и Auto

В C++ 14 можно использовать `decltype(auto)` без завершающего возвращаемого типа для объявления функции шаблона, тип возвращаемого значения которого зависит от типов своих аргументов шаблона.

В C++ 11 можно использовать описатель типа **decltype** для завершающего возвращаемого типа вместе с ключевым словом **Auto** , чтобы объявить функцию-шаблон, тип возвращаемого значения которого зависит от типов его аргументов шаблона. Например, рассмотрим следующий пример кода, в котором тип возвращаемого значения функции шаблона зависит от типов аргументов шаблона. В примере кода *неизвестный* заполнитель указывает, что тип возвращаемого значения не может быть указан.

```cpp
template<typename T, typename U>
UNKNOWN func(T&& t, U&& u){ return t + u; };
```

Введение описателя типа **decltype** позволяет разработчику получить тип выражения, возвращаемого функцией-шаблоном. Используйте *альтернативный синтаксис объявления функции* , который показан ниже, ключевое слово **Auto** и описатель типа **decltype** для объявления *позднего указанного* возвращаемого типа. Поздно заданный возвращаемый тип определяется, когда происходит компиляция, а не кодирование объявления.

Следующий прототип иллюстрирует синтаксис альтернативного объявления функции. Обратите внимание, что квалификаторы **const** и **volatile** , а также [спецификация исключения](../cpp/exception-specifications-throw-cpp.md) **throw** являются необязательными. Заполнитель *function_body* представляет составной оператор, указывающий, что делает функция. В качестве лучшего написания кода заполнитель *выражения* в инструкции **decltype** должен соответствовать выражению, заданному оператором **return** , если таковой имеется, в *function_body*.

**Auto** *function_name* **(** *Параметры*<sub>OPT</sub> **)** **const**<sub>opt</sub> **независимый**<sub>opt</sub> запрос opt **->** **decltype (** *выражение* **)** выдает<sub>неявное</sub> **исключение** **{** *function_body* **};**

В следующем примере кода поздно заданный возвращаемый тип функции шаблона `myFunc` определяется типами аргументов шаблона `t` и `u`. В качестве лучшего программирования в примере кода также используются ссылки rvalue и шаблон функции `forward`, поддерживающий *идеальную пересылку*. Дополнительные сведения см. в статье [Декларатор ссылки Rvalue: &&](../cpp/rvalue-reference-declarator-amp-amp.md).

```cpp
//C++11
template<typename T, typename U>
auto myFunc(T&& t, U&& u) -> decltype (forward<T>(t) + forward<U>(u))
        { return forward<T>(t) + forward<U>(u); };

//C++14
template<typename T, typename U>
decltype(auto) myFunc(T&& t, U&& u)
        { return forward<T>(t) + forward<U>(u); };
```

## <a name="decltype-and-forwarding-functions-c11"></a>Decltype и функции пересылки (C++ 11)

Функции пересылки создают программы-оболочек для вызовов других функций. Рассмотрим шаблон функции, который пересылает свои аргументы (или результаты выражения с этими аргументами) другой функции. Кроме того, функция пересылки возвращает результат вызова другой функции. В этом сценарии тип возвращаемого значения функции пересылки должен совпадать с типом возвращаемого значения функции в программе-оболочке.

В этом сценарии нельзя писать соответствующее выражение типа без описателя типа **decltype** . Описатель типа **decltype** позволяет использовать универсальные функции перенаправления, так как не теряет необходимых сведений о том, возвращает ли функция ссылочный тип. Пример кода функции пересылки см. в предыдущем примере шаблонной функции `myFunc`.

## <a name="example"></a>Пример

В следующем примере кода объявляется поздно заданный возвращаемый тип шаблонной функции `Plus()`. Функция `Plus` обрабатывает два операнда с помощью **оператора +** Overload. Следовательно, интерпретация добавочного оператора (+) и тип возвращаемого значения функции `Plus` зависят от типов аргументов функции.

```cpp
// decltype_1.cpp
// compile with: cl /EHsc decltype_1.cpp

#include <iostream>
#include <string>
#include <utility>
#include <iomanip>

using namespace std;

template<typename T1, typename T2>
auto Plus(T1&& t1, T2&& t2) ->
   decltype(forward<T1>(t1) + forward<T2>(t2))
{
   return forward<T1>(t1) + forward<T2>(t2);
}

class X
{
   friend X operator+(const X& x1, const X& x2)
   {
      return X(x1.m_data + x2.m_data);
   }

public:
   X(int data) : m_data(data) {}
   int Dump() const { return m_data;}
private:
   int m_data;
};

int main()
{
   // Integer
   int i = 4;
   cout <<
      "Plus(i, 9) = " <<
      Plus(i, 9) << endl;

   // Floating point
   float dx = 4.0;
   float dy = 9.5;
   cout <<
      setprecision(3) <<
      "Plus(dx, dy) = " <<
      Plus(dx, dy) << endl;

   // String
   string hello = "Hello, ";
   string world = "world!";
   cout << Plus(hello, world) << endl;

   // Custom type
   X x1(20);
   X x2(22);
   X x3 = Plus(x1, x2);
   cout <<
      "x3.Dump() = " <<
      x3.Dump() << endl;
}
```

```Output
Plus(i, 9) = 13
Plus(dx, dy) = 13.5
Hello, world!
x3.Dump() = 42
```

## <a name="example"></a>Пример

**Visual Studio 2017 и более поздние версии:** Компилятор анализирует аргументы decltype при объявлении шаблонов, а не на экземпляре. Соответственно, независимая специализация, обнаруженная в аргументе decltype, не откладывается до момента создания и немедленно обрабатывается. Кроме того, в это время выявляются все возникающие ошибки.

В следующем примере показана такая ошибка компилятора, возникающая во время объявления.

```cpp
#include <utility>
template <class T, class ReturnT, class... ArgsT> class IsCallable
{
public:
   struct BadType {};
   template <class U>
   static decltype(std::declval<T>()(std::declval<ArgsT>()...)) Test(int); //C2064. Should be declval<U>
   template <class U>
   static BadType Test(...);
   static constexpr bool value = std::is_convertible<decltype(Test<T>(0)), ReturnT>::value;
};

constexpr bool test1 = IsCallable<int(), int>::value;
static_assert(test1, "PASS1");
constexpr bool test2 = !IsCallable<int*, int>::value;
static_assert(test2, "PASS2");
```

## <a name="requirements"></a>Требования

Visual Studio 2010 или более поздние версии.

для `decltype(auto)` требуется Visual Studio 2015 или более поздней версии.
