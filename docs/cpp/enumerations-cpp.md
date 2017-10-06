---
title: "Перечисления (C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- enum_cpp
dev_langs:
- C++
helpviewer_keywords:
- declarations, enumerations
- enumerators, declaring
- enum keyword [C++]
- named constants, enumeration declarations
- declaring enumerations
ms.assetid: 081829db-5dca-411e-a53c-bffef315bcb3
caps.latest.revision: 27
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 5a28ef1a4330f3519a1084921d493b6595f31112
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="enumerations-c"></a>Перечисления (C++)
Перечисление — это пользовательский тип, состоящий из набора целочисленных констант, называемых перечислителями.  
  
> [!NOTE]
>  В этом разделе рассматривается тип `enum` языка C++ стандарта ISO, а также ограниченный (строго типизированный) тип `enum class`, который впервые введен в C++11. Сведения о `public enum class` или `private enum class` типов в C + +/ CLI и C + +/ CX см. в разделе [класс перечисления](../windows/enum-class-cpp-component-extensions.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
// unscoped enum:  
enum [identifier] [: type]  
{enum-list};   
  
// scoped enum:  
enum [class|struct]   
[identifier] [: type]   
{enum-list};  
```  
  
```  
// Forward declaration of enumerations  (C++11):  
enum A : int; // non-scoped enum must have type specified
enum class B; // scoped enum defaults to int but ...
enum class C : short;  // ... may have any integral underlying type
```  
  
## <a name="parameters"></a>Параметры  
 `identifier`  
 Имя типа, присваиваемое перечислению.  
  
 `type`  
 Базовый тип перечислителей; все перечислители имеют один базовый тип. Может быть любым целочисленным типом.  
  
 `enum-list`  
 Разделенный запятыми список перечислителей в перечислении. Каждый перечислитель или имя переменной в области должны быть уникальными. Однако значения могут повторяться. В неограниченном перечислении областью видимости является окружающая область; в ограниченном перечислении областью видимости является сам список `enum-list`.  В перечисление с ограниченной областью список может быть пустым в силе, который определяет новый целочисленный тип.
  
 `class`  
 Используя это ключевое слово в объявлении, вы указываете, что перечисление ограничено и необходимо предоставить `identifier`. Кроме того, ключевое слово `struct` используется вместо `class`, так как в этом контексте они семантически эквивалентны.  
  
## <a name="enumerator-scope"></a>Перечислитель области  
 Перечисление предоставляет контекст для описания диапазона значений, которые представлены в виде именованных констант и также называются перечислителями. В первоначальных типах перечислений C и C++ перечислители с неполным имеем являются видимыми внутри области видимости, в которой объявлено перечисление. В ограниченных перечислениях имя перечислителя должно уточняться именем типа перечисления. В следующем примере демонстрируется основное различие между двумя видами перечислений.  
  
```cpp  
namespace CardGame_Scoped  
{  
    enum class Suit { Diamonds, Hearts, Clubs, Spades };  
  
    void PlayCard(Suit suit)  
    {  
        if (suit == Suit::Clubs) // Enumerator must be qualified by enum type  
        { /*...*/}  
    }  
}  
  
namespace CardGame_NonScoped  
{  
    enum Suit { Diamonds, Hearts, Clubs, Spades };  
  
    void PlayCard(Suit suit)  
    {  
        if (suit == Clubs) // Enumerator is visible without qualification  
        { /*...*/  
        }  
    }  
}  
```  
  
 Каждому имени в перечислении присваивается целочисленное значение, которое соответствует определенному месту в порядке значений в перечислении. По умолчанию первому значению присваивается 0, следующему — 1 и т. д., но можно задать значение перечислителя явным образом, как показано ниже:  
  
```cpp  
enum Suit { Diamonds = 1, Hearts, Clubs, Spades };  
  
```  
  
 Перечислителю `Diamonds` присваивается значение `1`. Если последующим перечислителям не присваиваются явные значения, они получают значение предыдущего перечислителя плюс один. В предыдущем примере `Hearts` имел бы значение 2, `Clubs` — значение 3 и т.д.  
  
 Каждый перечислитель обрабатывается как константа; он должен иметь уникальное имя внутри области, в которой определяется тип `enum` (для неограниченных перечислений), или в самом перечислении (для ограниченных перечислений). Значения, задаваемые имена, могут быть неуникальными. Например, для следующего объявления неограниченного перечисления `Suit`:  
  
```cpp  
enum Suit { Diamonds = 5, Hearts, Clubs = 4, Spades };  
```  
  
 значения `Diamonds`, `Hearts`, `Clubs` и `Spades` равны 5, 6, 4 и 5 соответственно. Обратите внимание, что значение 5 используется несколько раз; это допускается, независимо от намерений разработчика. Такие же правила распространяются на ограниченные перечисления.  
  
 ## <a name="casting-rules"></a>Приведение правил  
  
 Неограниченные перечисления-константы могут неявно преобразовываться в тип `int`, но `int` никогда неявно не преобразуется в значение перечисления. В следующем примере показано, что пройдет при попытке присвоить переменной `hand` значение, не относящееся к типу `Suit`:  
  
```cpp  
int account_num = 135692;  
Suit hand;  
hand = account_num; // error C2440: '=' : cannot convert from 'int' to 'Suit'  
  
```  
  
 Для преобразования значения `int` в ограниченный или неограниченный перечислитель потребуется приведение. Однако неограниченный перечислитель можно преобразовать в целочисленное значение без приведения.  
  
```cpp  
int account_num = Hearts; //OK if Hearts is in a unscoped enum  
```  
  
 Использование подобных неявных преобразований может приводить к непредвиденным побочным эффектам. Чтобы избежать ошибок программирования, связанных с неограниченными перечислениями, значения ограниченных перечислений являются строго типизированными. Ограниченные перечислители должны уточняться именем типа перечисления (идентификатором); они не могут быть неявно преобразованы, как показано в следующем примере:  
  
```cpp  
namespace ScopedEnumConversions  
{  
    enum class Suit { Diamonds, Hearts, Clubs, Spades };  
  
    void AttemptConversions()  
    {  
        Suit hand;   
        hand = Clubs; // error C2065: 'Clubs' : undeclared identifier  
        hand = Suit::Clubs; //Correct.  
        int account_num = 135692;  
        hand = account_num; // error C2440: '=' : cannot convert from 'int' to 'Suit'  
        hand = static_cast<Suit>(account_num); // OK, but probably a bug!!!  
  
        account_num = Suit::Hearts; // error C2440: '=' : cannot convert from 'Suit' to 'int'  
        account_num = static_cast<int>(Suit::Hearts); // OK  
}  
  
```  
  
 Обратите внимание, что в строке `hand = account_num;` по-прежнему содержится ошибка, которая происходит при использовании неограниченных перечислений, как показано выше. Эта ошибка устраняется с помощью явного приведения. Однако при использовании ограниченных перечислений попытка преобразования в следующем операторе — `account_num = Suit::Hearts;` — больше не будет разрешена без явного приведения. 

## <a name="enums-with-no-enumerators"></a>Перечислимые типы с не перечислителей
**Visual Studio 2017 г 15,3 и более поздних версий** (с [/std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): путем определения перечисления (регулярно или с заданной областью) с помощью явного базового типа и не перечислителей, можно фактически ввести новый целочисленного типа, не имеет неявного преобразования к любому другому типу. С помощью этого типа, а не встроенных базового типа, можно устранить возможную незначительные ошибки, вызванные непреднамеренное неявных преобразований.  


```cpp
enum class byte : unsigned char { };
```

Новый тип является точную копию базового типа и поэтому имеет соглашение о вызове, что означает, что он может использоваться между ABIs без снижения производительности. Преобразование не требуется, когда переменные типа инициализируются с помощью прямого списка инициализации. В следующем примере показана инициализация перечислимые типы с не перечислителей в различных контекстах:

```cpp
enum class byte : unsigned char { };

enum class E : int { };
E e1{ 0 };
E e2 = E{ 0 };

struct X 
{
    E e{ 0 };
    X() : e{ 0 } { }
};

E* p = new E{ 0 }; 

void f(E e) {};

int main()
{
    f(E{ 0 });
    byte i{ 42 };
    byte j = byte{ 42 };

    // unsigned char c = j; // C2440: 'initializing': cannot convert from 'byte' to 'unsigned char'
    return 0;
}
``` 
  
## <a name="see-also"></a>См. также  
 [Объявления перечислений C](../c-language/c-enumeration-declarations.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)
