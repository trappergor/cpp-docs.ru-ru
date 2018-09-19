---
title: decltype (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- decltype_cpp
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], decltype
- decltype operator
- operators [C++], type of an expression
- operators [C++], deduce expression type
ms.assetid: 6dcf8888-8196-4f13-af50-51e3797255d4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1c6cab68cd351c64d65eeed1eeffda7bf49385aa
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46074023"
---
# <a name="decltype--c"></a>decltype (C++)

**Decltype** описатель типа предоставляет тип заданного выражения. **Decltype** описатель типа вместе с [ключевое слово auto](../cpp/auto-cpp.md), используется главным образом для разработчиков, которые создают библиотеки шаблонов. Используйте **автоматически** и **decltype** для объявления функции шаблона возвращаемого значения которой тип зависит от типов аргументов его шаблонов. Также можно использовать **автоматически** и **decltype** для объявления функции шаблона, который создает оболочку для вызова другой функции, а затем возвращает тип возвращаемого значения функции в оболочке.

## <a name="syntax"></a>Синтаксис

```
decltype( expression )
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*Выражение*|Выражения. Дополнительные сведения см. в разделе [выражения](../cpp/expressions-cpp.md).|

## <a name="return-value"></a>Возвращаемое значение

Тип *выражение* параметра.

## <a name="remarks"></a>Примечания

**Decltype** спецификатор типа поддерживается в Visual C++ 2010 или более поздней версии и может использоваться с машинный или управляемый код. `decltype(auto)` (C++ 14) поддерживается в Visual Studio 2015 и более поздних версиях.

Компилятор использует следующие правила для определения типа *выражение* параметра.

- Если *выражение* параметр — это идентификатор или [доступ к члену класса](../cpp/member-access-operators-dot-and.md), `decltype(expression)` — это тип сущности, с именем *выражение*. Если сущность отсутствует или *выражение* параметр именует набор перегруженных функций, компилятор создает сообщение об ошибке.

- Если *выражение* параметр представляет собой вызов функции или перегруженной функцией оператора, `decltype(expression)` является возвращаемым типом функции. Скобки вокруг перегруженного оператора игнорируются.

- Если *выражение* параметр [rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md), `decltype(expression)` — это тип *выражение*. Если *выражение* параметр [lvalue](../cpp/lvalues-and-rvalues-visual-cpp.md), `decltype(expression)` — [ссылки lvalue](../cpp/lvalue-reference-declarator-amp.md) типу *выражение*.

В следующем примере кода показано несколько способов использования **decltype** описателя типа. Допустим, во-первых, что были закодированы следующие операторы.

```cpp
int var;
const int&& fx();
struct A { double x; }
const A* a = new A();
```

Затем изучите типы, возвращаемые четыре **decltype** инструкции в следующей таблице.

|Оператор|Тип|Примечания|
|---------------|----------|-----------|
|`decltype(fx());`|`const int&&`|[Ссылку rvalue](../cpp/rvalue-reference-declarator-amp-amp.md) для **const int**.|
|`decltype(var);`|**int**|Тип переменной `var`.|
|`decltype(a->x);`|**double**|Тип членского доступа.|
|`decltype((a->x));`|`const double&`|Внутренние скобки вызывают оценку оператора в качестве выражения, а не членского доступа. И поскольку `a` объявляется как `const` указателя, тип является ссылкой на **const двойной**.|

## <a name="decltype-and-auto"></a>Decltype и Auto

В C ++ 14, можно использовать `decltype(auto)` с без завершающего типа возвращаемого значения для объявления функции шаблона, тип возвращаемого значения которой зависит от типов аргументов его шаблонов.

В C ++ 11, можно использовать **decltype** описателя на завершающего типа возвращаемого значения типа вместе с **автоматически** ключевого слова для объявления функции шаблона, тип возвращаемого значения которой зависит от типов его шаблона аргументы. Например, рассмотрим следующий пример кода, в котором тип возвращаемого значения функции шаблона зависит от типов аргументов шаблона. В примере кода *Неизвестный* заполнителя указывает, что не может быть указан тип возвращаемого значения.

```cpp
template<typename T, typename U>
UNKNOWN func(T&& t, U&& u){ return t + u; };
```

Введение **decltype** спецификатор типа позволяет разработчику получить тип выражения, которое возвращает функция шаблона. Используйте *альтернативный синтаксис объявления функций* см. ниже, **автоматически** ключевое слово и **decltype** описатель для объявления типа  *поздно заданный* тип возвращаемого значения. Поздно заданный тип возвращаемого значения определяется, когда происходит компиляция, а не кодирование объявления.

Следующий прототип иллюстрирует синтаксис альтернативного объявления функции. Обратите внимание, что **const** и **volatile** квалификаторы и **throw** [спецификация исключений](../cpp/exception-specifications-throw-cpp.md) являются необязательными. *Function_body* заполнитель представляет составную инструкцию, которая определяет действия функции. В написании кода рекомендуется *выражение* местозаполнителя в **decltype** инструкции должно соответствовать выражению, заданному **возвращают** инструкции, если таковой имеется, в *function_body*.

**Автоматическое** *имя_функции* **(** *параметры*<sub>opt</sub> **)**  **const**<sub>opt</sub> **volatile**<sub>opt</sub> **->** **decltype (** *выражение* **)** **throw**<sub>opt</sub> **{** *function_body* **};**

В следующем примере кода поздно заданный возвращаемый тип функции шаблона `myFunc` определяется типами аргументов шаблона `t` и `u`. Как лучшие методы программирования, в примере кода также используются ссылки rvalue и `forward` шаблон функции, которая поддерживает *точную пересылку*. Дополнительные сведения см. в статье [Декларатор ссылки Rvalue: &&](../cpp/rvalue-reference-declarator-amp-amp.md).

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

В этом случае нельзя записывать подобающее выражение типа без **decltype** описателя типа. **Decltype** спецификатор типа включает универсальные функции пересылки, так как он не теряет необходимой информации о, возвращает ли функция ссылочный тип. Пример кода функции пересылки см. в предыдущем примере шаблонной функции `myFunc`.

## <a name="example"></a>Пример

В следующем примере кода объявляется поздно заданный возвращаемый тип шаблонной функции `Plus()`. `Plus` Функция обрабатывает два свои операнда с **оператор +** перегрузки. Следовательно, интерпретация добавочного оператора (+) и возвращаемый тип функции `Plus` зависят от типов аргументов функции.

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

**Visual Studio 2017 и более поздних версий:** компилятор анализирует аргументы decltype при шаблоны объявлении, а не создан. Соответственно, независимая специализация, обнаруженная в аргументе decltype, не откладывается до момента создания и немедленно обрабатывается. Кроме того, в это время выявляются все возникающие ошибки.

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

Visual C++ 2010 и выше.

`decltype(auto)` требуется Visual Studio 2015 или более поздней версии.