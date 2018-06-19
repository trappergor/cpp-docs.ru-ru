---
title: Многоточия и шаблоны с переменным числом аргументов | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: f20967d9-c967-4fd2-b902-2bb1d5ed87e3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2eddd87660d996e0d726c4453e0eb732a5553b99
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32416662"
---
# <a name="ellipses-and-variadic-templates"></a>Многоточия и шаблоны с переменными аргументами
В этой статье показано, как использовать многоточие (`...`) в шаблонах C++ с переменным числом аргументов. Многоточие множество применений в C и C++. Они вводят переменные списки аргументов для функций. Одним из наиболее известных примеров является функция `printf()` из библиотеки времени выполнения C .  
  
 Объект *с переменным числом аргументов шаблона* — это шаблон класса или функции, поддерживающий произвольное число аргументов. Этот механизм особенно удобен для разработчиков библиотек C++, поскольку его можно применить к как к шаблонам классов, так и к шаблонам функций. Таким образом, он предоставляет широкий спектр широкий спектр типобезопасных и нетривиальных функций и гибких возможностей.  
  
## <a name="syntax"></a>Синтаксис  
 В шаблонах шаблонами с переменным числом аргументов многоточие используется двумя способами. Слева от имени параметра оно означает *пакет параметров*, а справа от имени параметра, он расширяет пакетов параметров в отдельные имена.  
  
 Ниже приведен простой пример из *шаблонного класса* определения синтаксиса:  
  
```cpp  
template<typename... Arguments> class classname;  
```  
  
 В обоих случаях (как при введении пакета параметров, так и при его развертывании) вокруг многоточия можно оставить пробельные символы, как показано в этом примере:  
  
```cpp  
template<typename ...Arguments> class classname;  
```  
  
 Или в этом:  
  
```cpp  
template<typename ... Arguments> class classname;  
```  
  
 Обратите внимание, что в этой статье используется соглашение, показанное в первом примере (многоточие примыкает к имени типа — `typename`).  
  
 В приведенных выше примерах параметр `Arguments` означает пакет параметров. Класс `classname` может принимать переменное число аргументов, как показано в следующих примерах:  
  
```cpp  
template<typename... Arguments> class vtclass;  
  
vtclass< > vtinstance1;  
vtclass<int> vtinstance2;  
vtclass<float, bool> vtinstance3;  
vtclass<long, std::vector<int>, std::string> vtinstance4;  
  
```  
  
 Кроме того, определение шаблонного класса с переменным числом аргументов может устанавливать требование о том, что должен быть передан по меньшей мере один параметр:  
  
```cpp  
template <typename First, typename... Rest> class classname;  
  
```  
  
 Ниже приведен простой пример из *шаблонной функции* синтаксис:  
  
```cpp  
template <typename... Arguments> returntype functionname(Arguments... args);  
```  
  
 `Arguments` Пакет параметров затем развертывается для использования, как показано в следующем разделе **основные сведения о шаблонах с переменным числом аргументов**.  
  
 Возможны и другие формы синтаксиса шаблонной функции с переменным количеством аргументов возможны. Некоторые примеры приведены ниже.  
  
```cpp  
template <typename... Arguments> returntype functionname(Arguments&... args);   
template <typename... Arguments> returntype functionname(Arguments&&... args);  
template <typename... Arguments> returntype functionname(Arguments*... args);  
```  
  
 Также допускаются спецификаторы, например `const`.  
  
```cpp  
template <typename... Arguments> returntype functionname(const Arguments&... args);  
  
```  
  
 Шаблонные функции с переменным числом аргументов (как и аналогичные шаблонные классы) также могут устанавливать требование о том, что должен быть передан по меньшей мере один параметр.  
  
```cpp  
template <typename First, typename... Rest> returntype functionname(const First& first, const Rest&... args);  
  
```  
  
 В шаблонах с переменным числом аргументов используется оператор `sizeof...()` (он не имеет отношения к старому оператору `sizeof()`).  
  
```cpp  
template<typename... Arguments>  
void tfunc(const Arguments&... args)  
{  
    constexpr auto numargs{ sizeof...(Arguments) };  
  
    X xobj[numargs]; // array of some previously defined type X  
  
    helper_func(xobj, args...);  
}  
  
```  
  
## <a name="more-about-ellipsis-placement"></a>Дополнительные сведения о положении многоточия  
 Выше в этой статье говорилось, что если многоточие определяет пакеты параметров и их развертывание, то "Слева от имени параметра оно означает пакет параметров, а справа от имени параметра оно служит для развертывания пакетов параметров в отдельные имена". Технически это верно, но может порождать неоднозначности при трансляции в код. Рассмотрим этот пример:  
  
-   В шаблоне список параметров (`template <parameter-list>`), `typename...` представляет пакет параметров шаблона.  
  
-   В параметр предложения объявления (`func(parameter-list)`), «верхнего уровня» многоточие представляет пакет параметров функции и позиционирования многоточие важно:  
  
    ```cpp  
    // v1 is NOT a function parameter pack:  
    template <typename... Types> void func1(std::vector<Types...> v1);   
  
    // v2 IS a function parameter pack:  
    template <typename... Types> void func2(std::vector<Types>... v2);   
    ```  
  
-   Там, где многоточие стоит непосредственно за именем параметра, оно используется для развертывания пакета параметров.  
  
## <a name="example"></a>Пример  
 Механизм действия шаблонных функций с переменным числом аргументов можно проиллюстрировать на показательном примере — переписать с ее использованием какую-либо функциональность `printf`:  
  
```cpp  
#include <iostream>  
  
using namespace std;  
  
void print() {  
    cout << endl;  
}  
  
template <typename T> void print(const T& t) {  
    cout << t << endl;  
}  
  
template <typename First, typename... Rest> void print(const First& first, const Rest&... rest) {  
    cout << first << ", ";  
    print(rest...); // recursive call using pack expansion syntax  
}  
  
int main()  
{  
    print(); // calls first overload, outputting only a newline  
    print(1); // calls second overload  
  
    // these call the third overload, the variadic template,   
    // which uses recursion as needed.  
    print(10, 20);  
    print(100, 200, 300);  
    print("first", 2, "third", 3.14159);  
}  
  
```  
  
## <a name="output"></a>Вывод  
  
```  
  
1  
10, 20  
100, 200, 300  
first, 2, third, 3.14159  
```  
  
> [!NOTE]
>  Большинство реализаций, включающие функции с переменным числом аргументов шаблона использовать рекурсию некоторые формы, но немного отличается от традиционных рекурсии.  Традиционные рекурсия заключается в функцию, вызывает сам себя, используя ту же сигнатуру. (Это может быть перегрузка или шаблон, но каждый раз выбирается одна и та же сигнатура.) Рекурсия с переменным числом аргументов заключается в вызове шаблона функции с переменным числом аргументов посредством использования другого (почти всегда уменьшающегося) числа аргументов. Таким образом, каждый раз отбрасывается новая сигнатура. "Базовый случай" по-прежнему является обязательным, но природа рекурсии отличается.  
  
