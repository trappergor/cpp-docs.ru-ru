---
title: "-Zc: implicitNoexcept (неявные спецификаторы исключений) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /Zc:implicitNoexcept
dev_langs: C++
helpviewer_keywords:
- /Zc:implicitNoexcept
- Zc:implicitNoexcept
- -Zc:implicitNoexcept
ms.assetid: 71807652-6f9d-436b-899e-f52daa6f500b
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 20789d226ace8ba41a9635f0039274b68d37922c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="zcimplicitnoexcept-implicit-exception-specifiers"></a>/Zc:implicitNoexcept (неявные спецификаторы исключений)
Когда **/Zc: implicitnoexcept** параметр указан, компилятор добавляет неявный [noexcept](../../cpp/noexcept-cpp.md) описатель исключения для заданного компилятором специальные функции-члены и пользовательские деструкторы и методы освобождения. По умолчанию **/Zc: implicitnoexcept** включена в соответствии с ISO C ++ 11 standard. Отключение этого параметра отключает неявный `noexcept` для пользовательских деструкторов и методов освобождения, а также заданных компилятором специальных функций-членов.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
/Zc:implicitNoexcept[-]  
```  
  
#### <a name="parameters"></a>Параметры  
  
## <a name="remarks"></a>Примечания  
 По умолчанию и если **/Zc: implicitnoexcept** указан, компилятор следует разделу 15.4 ISO стандарте C ++ 11 и неявным образом добавляет `noexcept` описатель исключения каждому объявленную неявно или явно установленные по умолчанию Специальная функция-член — конструктор по умолчанию, конструктор копии, конструктор перемещения, деструктор, оператор присваивания копии или оператор присваивания перемещения и каждый определяемых пользователем деструктор или функцию освобождения. Определяемый пользователем метод освобождения содержит неявный описатель исключения `noexcept(true)`. Для пользовательских деструкторов неявный описатель исключение — `noexcept(true)`, если во внутреннем классе члена или базовом классе нет деструктора, отличного от типа `noexcept(true)`. Если для созданных компилятором специальных функций-членов любая функция, вызываемая напрямую этой функцией, фактически является `noexcept(false)`, а неявный описатель исключения — `noexcept(false)`. Иначе неявный описатель исключение — `noexcept(true)`.  
  
 Компилятор не создает неявный описатель исключения для функций, объявленных с явными описателями `noexcept` и `throw` или атрибутом `__declspec(nothrow)`.  
  
 Если этот параметр отключен, указав **Zc: implicitnoexcept**, неявные описатели исключений созданных компилятором. То же самое происходит в Visual Studio 2013, где в деструкторах и методах освобождения без описателей исключений могли быть операторы `throw`. По умолчанию и когда **/Zc: implicitnoexcept** указан, если `throw` встречается во время выполнения в функции с неявным `noexcept(true)` спецификатор, он заставляет непосредственный вызов `std::terminate`, и нормальное поведение очистки для обработчиков исключений не гарантируется. Для идентификации этой ситуации компилятор создает [Предупреждение компилятора (уровень 1) C4297](../../error-messages/compiler-warnings/compiler-warning-level-1-c4297.md). Если `throw` — преднамеренно, мы рекомендуем вам использовать в объявлении функции явный `noexcept(false)` описатель вместо **Zc: implicitnoexcept**.  
  
 В этом примере показано, как пользовательский деструктор без явного описателя исключения имеет ведет себя, если **/Zc: implicitnoexcept** задан или отключен параметр. Для демонстрации поведения при установке, компиляция с помощью `cl /EHsc /W4 implicitNoexcept.cpp`. Для демонстрации поведения при отключении, компиляция с помощью `cl /EHsc /W4 /Zc:implicitNoexcept- implicitNoexcept.cpp`.  
  
```  
// implicitNoexcept.cpp  
// Compile by using: cl /EHsc /W4 implicitNoexcept.cpp  
// Compile by using: cl /EHsc /W4 /Zc:implicitNoexcept- implicitNoexcept.cpp  
  
#include <iostream>  
#include <cstdlib>      // for std::exit, EXIT_FAILURE, EXIT_SUCCESS  
#include <exception>    // for std::set_terminate  
  
void my_terminate()  
{  
    std::cout << "Unexpected throw caused std::terminate" << std::endl;  
    std::cout << "Exit returning EXIT_FAILURE" << std::endl;  
    std::exit(EXIT_FAILURE);  
}  
  
struct A {  
    // Explicit noexcept overrides implicit exception specification  
    ~A() noexcept(false) {  
        throw 1;  
    }  
};  
  
struct B : public A {  
    // Compiler-generated ~B() definition inherits noexcept(false)  
    ~B() = default;  
};  
  
struct C {  
    // By default, the compiler generates an implicit noexcept(true)  
    // specifier for this user-defined destructor. To enable it to  
    // throw an exception, use an explicit noexcept(false) specifier,  
    // or compile by using /Zc:implicitNoexcept-  
    ~C() {    
        throw 1; // C4297, calls std::terminate() at run time  
    }  
};  
  
struct D : public C {  
    // This destructor gets the implicit specifier of its base.  
    ~D() = default;  
};  
  
int main()  
{  
    std::set_terminate(my_terminate);  
  
    try  
    {  
        {  
            B b;   
        }  
    }  
    catch (...)  
    {  
        // exception should reach here in all cases  
        std::cout << "~B Exception caught" << std::endl;  
    }  
    try  
    {  
        {  
            D d;  
        }  
    }  
    catch (...)  
    {  
        // exception should not reach here if /Zc:implicitNoexcept  
        std::cout << "~D Exception caught" << std::endl;  
    }  
    std::cout << "Exit returning EXIT_SUCCESS" << std::endl;  
    return EXIT_SUCCESS;  
}  
  
```  
  
 При компиляции с параметром по умолчанию **/Zc: implicitnoexcept**, образец создает следующие выходные данные:  
  
```Output  
~B Exception caught  
Unexpected throw caused std::terminate  
Exit returning EXIT_FAILURE  
```  
  
 При компиляции с помощью параметра **Zc: implicitnoexcept**, образец создает следующие выходные данные:  
  
```Output  
~B Exception caught  
~D Exception caught  
Exit returning EXIT_SUCCESS  
```  
  
 Дополнительные сведения о вопросах соответствия в Visual C++ см. в статье [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Выберите **C/C++** папки.  
  
3.  Выберите **командной строки** страницу свойств.  
  
4.  Изменить **Дополнительные параметры** включив **/Zc: implicitnoexcept** или **Zc: implicitnoexcept** и выберите **ОК**.  
  
## <a name="see-also"></a>См. также  
 [/Zc (соответствие)](../../build/reference/zc-conformance.md)   
 [noexcept](../../cpp/noexcept-cpp.md)   
 [Спецификации исключений (throw)](../../cpp/exception-specifications-throw-cpp.md)   
 [terminate](../../standard-library/exception-functions.md#terminate)