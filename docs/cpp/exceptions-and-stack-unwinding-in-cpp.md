---
title: Исключения и освобождение стека в C++
ms.date: 11/19/2019
ms.assetid: a1a57eae-5fc5-4c49-824f-3ce2eb8129ed
ms.openlocfilehash: 11657206e86dbc81eb62c1e11b49fd87777f11d8
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246572"
---
# <a name="exceptions-and-stack-unwinding-in-c"></a>Исключения и освобождение стека в C++

В механизме исключений C++ элемент управления перемещается из оператора throw в первый оператор catch, который может обработать выданный тип. When the catch statement is reached, all of the automatic variables that are in scope between the throw and catch statements are destroyed in a process that is known as *stack unwinding*. При очистке стека выполнение продолжается следующим образом.

1. Control reaches the **try** statement by normal sequential execution. The guarded section in the **try** block is executed.

1. If no exception is thrown during execution of the guarded section, the **catch** clauses that follow the **try** block are not executed. Execution continues at the statement after the last **catch** clause that follows the associated **try** block.

1. If an exception is thrown during execution of the guarded section or in any routine that the guarded section calls either directly or indirectly, an exception object is created from the object that is created by the **throw** operand. (This implies that a copy constructor may be involved.) At this point, the compiler looks for a **catch** clause in a higher execution context that can handle an exception of the type that is thrown, or for a **catch** handler that can handle any type of exception. The **catch** handlers are examined in order of their appearance after the **try** block. If no appropriate handler is found, the next dynamically enclosing **try** block is examined. This process continues until the outermost enclosing **try** block is examined.

1. Если соответствующий обработчик по-прежнему не найден или исключение возникает во время процесса очистки до получения элемента управления обработчиком, вызывается предопределенная функция времени выполнения `terminate`. Если исключение возникает после создания исключения, но до начала процесса очистки, вызывается функция `terminate`.

1. If a matching **catch** handler is found, and it catches by value, its formal parameter is initialized by copying the exception object. Если обработчик выполняет перехват по ссылке, параметр инициализируется для ссылки на объект исключения. После инициализации формального параметра начинается процесс очистки стека. This involves the destruction of all automatic objects that were fully constructed—but not yet destructed—between the beginning of the **try** block that is associated with the **catch** handler and the throw site of the exception. Удаление происходит в порядке, обратном созданию. The **catch** handler is executed and the program resumes execution after the last handler—that is, at the first statement or construct that is not a **catch** handler. Control can only enter a **catch** handler through a thrown exception, never through a **goto** statement or a **case** label in a **switch** statement.

## <a name="stack-unwinding-example"></a>Stack unwinding example

В следующем примере показано, как очистить стек при создании исключения. Выполнение потока переходит от оператора throw в `C` к оператору catch в `main`, и при этом удаляются все функции. Обратите внимание, что порядок создания и удаления объектов `Dummy` соответствует порядку их выхода из области видимости. Также обратите внимание, что завершается выполнение только функции `main`, содержащей оператор catch. Функция `A` никогда не возвращается после вызова `B()`, и `B` никогда не возвращается после вызова `C()`. Обратите внимание, что если раскомментировать определение указателя `Dummy` и соответствующую инструкцию DELETE, а затем запустить программу, указатель не удаляется. Это показывает, что может произойти, если функции не предоставляют гарантию исключения. Дополнительные сведения см. в разделе "Практическое руководство. Разработка исключений". Если закомментировать оператор catch, можно наблюдать за тем, что происходит при завершении выполнения программы в результате необработанного исключения.

```cpp
#include <string>
#include <iostream>
using namespace std;

class MyException{};
class Dummy
{
    public:
    Dummy(string s) : MyName(s) { PrintMsg("Created Dummy:"); }
    Dummy(const Dummy& other) : MyName(other.MyName){ PrintMsg("Copy created Dummy:"); }
    ~Dummy(){ PrintMsg("Destroyed Dummy:"); }
    void PrintMsg(string s) { cout << s  << MyName <<  endl; }
    string MyName;
    int level;
};

void C(Dummy d, int i)
{
    cout << "Entering FunctionC" << endl;
    d.MyName = " C";
    throw MyException();

    cout << "Exiting FunctionC" << endl;
}

void B(Dummy d, int i)
{
    cout << "Entering FunctionB" << endl;
    d.MyName = "B";
    C(d, i + 1);
    cout << "Exiting FunctionB" << endl;
}

void A(Dummy d, int i)
{
    cout << "Entering FunctionA" << endl;
    d.MyName = " A" ;
  //  Dummy* pd = new Dummy("new Dummy"); //Not exception safe!!!
    B(d, i + 1);
 //   delete pd;
    cout << "Exiting FunctionA" << endl;
}

int main()
{
    cout << "Entering main" << endl;
    try
    {
        Dummy d(" M");
        A(d,1);
    }
    catch (MyException& e)
    {
        cout << "Caught an exception of type: " << typeid(e).name() << endl;
    }

    cout << "Exiting main." << endl;
    char c;
    cin >> c;
}

/* Output:
    Entering main
    Created Dummy: M
    Copy created Dummy: M
    Entering FunctionA
    Copy created Dummy: A
    Entering FunctionB
    Copy created Dummy: B
    Entering FunctionC
    Destroyed Dummy: C
    Destroyed Dummy: B
    Destroyed Dummy: A
    Destroyed Dummy: M
    Caught an exception of type: class MyException
    Exiting main.

*/
```
