---
title: Руководство. проектирование безопасности исключений
ms.custom: how-to
ms.date: 11/19/2019
ms.topic: conceptual
ms.assetid: 19ecc5d4-297d-4c4e-b4f3-4fccab890b3d
ms.openlocfilehash: 732a46166c99396c5d55a7d2acd834b58f3d2b2e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87187807"
---
# <a name="how-to-design-for-exception-safety"></a>Руководство. проектирование безопасности исключений

Одним из преимуществ механизма исключения является то, что выполнение вместе с данными об исключении переходит непосредственно из оператора, который создает исключение, в первую инструкцию Catch, которая его обрабатывает. Обработчик может иметь любое количество уровней вверх в стеке вызовов. Функции, которые вызываются между оператором try и оператором throw, не обязательно должны знать какие-либо сведения о возникшем исключении.  Однако они должны быть спроектированы таким образом, чтобы они могли выйти из области "непредвиденно" в любой момент, где исключение может быть распространено ниже, и сделать это без выхода из частично созданных объектов, утечки памяти или структур данных, которые находятся в непригодных для использования состояниях.

## <a name="basic-techniques"></a>Основные методы

Надежная политика обработки исключений требует тщательного мышления и должна быть частью процесса разработки. Как правило, большинство исключений обнаруживаются и создаются на нижних уровнях программного модуля, но обычно эти уровни не имеют достаточного контекста для устранения ошибки или предоставления сообщения конечным пользователям. В средних слоях функции могут перехватывать и выдавать исключения, когда необходимо проверить объект исключения, или у них есть дополнительная полезная информация для верхнего уровня, который в конечном итоге перехватывает исключение. Функция должна перехватывать и "проглотить" исключение, только если оно может полностью восстановиться из нее. Во многих случаях правильное поведение на средних уровнях заключается в том, чтобы разрешить распространение исключения вверх по стеку вызовов. Даже на самом верхнем уровне может быть целесообразно позволить необработанному исключению завершить программу, если исключение покидает программу в состоянии, в котором ее правильность не гарантируется.

Независимо от того, как функция обрабатывает исключение, чтобы гарантировать, что оно является "типобезопасным", оно должно быть спроектировано согласно следующим основным правилам.

### <a name="keep-resource-classes-simple"></a>Простота сохранения классов ресурсов

При инкапсулировании управления ресурсами вручную в классах используйте класс, который не выполняет никаких действий, кроме управления одним ресурсом. Благодаря простоте использования класса вы снижаете риск возникновения утечек ресурсов. Используйте [смарт-указатели](smart-pointers-modern-cpp.md) , если это возможно, как показано в следующем примере. Этот пример намеренно искусственно и упрощен, чтобы выделить различия при `shared_ptr` использовании.

```cpp
// old-style new/delete version
class NDResourceClass {
private:
    int*   m_p;
    float* m_q;
public:
    NDResourceClass() : m_p(0), m_q(0) {
        m_p = new int;
        m_q = new float;
    }

    ~NDResourceClass() {
        delete m_p;
        delete m_q;
    }
    // Potential leak! When a constructor emits an exception,
    // the destructor will not be invoked.
};

// shared_ptr version
#include <memory>

using namespace std;

class SPResourceClass {
private:
    shared_ptr<int> m_p;
    shared_ptr<float> m_q;
public:
    SPResourceClass() : m_p(new int), m_q(new float) { }
    // Implicitly defined dtor is OK for these members,
    // shared_ptr will clean up and avoid leaks regardless.
};

// A more powerful case for shared_ptr

class Shape {
    // ...
};

class Circle : public Shape {
    // ...
};

class Triangle : public Shape {
    // ...
};

class SPShapeResourceClass {
private:
    shared_ptr<Shape> m_p;
    shared_ptr<Shape> m_q;
public:
    SPShapeResourceClass() : m_p(new Circle), m_q(new Triangle) { }
};
```

### <a name="use-the-raii-idiom-to-manage-resources"></a>Использование идиомы RAII для управления ресурсами

Чтобы обеспечить безопасность исключений, функция должна гарантировать, что объекты, выделенные с помощью или, `malloc` **`new`** уничтожаются, и все ресурсы, такие как дескрипторы файлов, закрываются или освобождаются, даже если возникает исключение. Функция *получения ресурсов — инициализация* (RAII) идиома связывает такие ресурсы с сроком службы автоматических переменных. Если функция выходит за пределы области действия, либо путем возвращения обычно или из-за исключения, вызываются деструкторы для всех полностью сформированных автоматических переменных. Объект-оболочка RAII, такой как интеллектуальный указатель, вызывает соответствующую функцию DELETE или Close в своем деструкторе. В коде, защищенном с исключением, очень важно немедленно передавать владение каждым ресурсом объекту RAII. Обратите внимание, что `vector` классы,, `string` `make_shared` , `fstream` и схожие по себе обрабатывали ресурсы для получения.  Однако `unique_ptr` традиционные `shared_ptr` конструкции являются специальными, так как получение ресурса выполняется пользователем, а не объектом. Следовательно, они считаются *освобождением ресурсов* , но их можно считать RAII.

## <a name="the-three-exception-guarantees"></a>Три гарантии исключений

Как правило, безопасность исключений обсуждается в трех исключениях, которые гарантируют, что функция может предоставить следующие возможности: *гарантия отсутствия ошибок*, *строгая гарантия*и *Базовая гарантия*.

### <a name="no-fail-guarantee"></a>Гарантия No — сбой

Гарантия «без ошибок» (или «без выдачи») является самой высокой гарантией, которую может предоставить функция. Он указывает, что функция не будет вызывать исключение или разрешить распространение. Однако нельзя гарантировать такую гарантию, если (a) известно, что все функции, которые вызывает эта функция, также не являются ошибками, или (б) известно, что все возникшие исключения перехватываются до того, как они достигли этой функции, или (c) вы узнали, как перехватить и правильно обрабатывайте все исключения, которые могут достичь этой функции.

Как строгая гарантия, так и Базовая гарантия основываются на предположении, что деструкторы являются неуспешными. Все контейнеры и типы в стандартной библиотеке гарантируют, что их деструкторы не вызывают исключение. Существует также и обратное требование: Стандартная библиотека требует, чтобы определяемые пользователем типы, например, в качестве аргументов шаблона, не создавали деструкторы без вызова.

### <a name="strong-guarantee"></a>Строгая гарантия

Строгая гарантия указывает, что если функция выходит за пределы области действия из-за исключения, она не будет приводить к утечке памяти, а состояние программы не будет изменено. Функция, обеспечивающая строгую гарантию, по сути, является транзакцией, которая имеет семантику фиксации или отката: либо полностью завершается успешно, либо не оказывает никакого воздействия.

### <a name="basic-guarantee"></a>Базовая гарантия

Основная гарантия является слабой из трех. Тем не менее, это может быть лучшим выбором, когда строгая гарантия является слишком дорогостоящей в потреблении памяти или производительности. Основная гарантия указывает, что при возникновении исключения память не утечка, и объект остается в рабочем состоянии, даже если данные могли быть изменены.

## <a name="exception-safe-classes"></a>Классы, защищенные с исключением

Класс помогает обеспечить собственную безопасность исключений, даже если она используется небезопасными функциями, предотвращая ее частичное построение или частичное уничтожение. Если конструктор класса завершает работу до завершения, объект никогда не создается и его деструктор никогда не вызывается. Хотя автоматические переменные, инициализированные до исключения, будут вызывать свои деструкторы, динамически выделенная память или ресурсы, не управляемые смарт-указателем или аналогичной автоматической переменной, будут утеряны.

Встроенные типы являются неудачными, а стандартные типы библиотек поддерживают базовую гарантию как минимум. Следуйте этим рекомендациям для любого определяемого пользователем типа, который должен быть защищен от исключений.

- Для управления всеми ресурсами используйте смарт-указатели или другие оболочки типа RAII. Избегайте функций управления ресурсами в деструкторе класса, так как деструктор не будет вызываться, если конструктор выдаст исключение. Однако если класс является выделенным диспетчером ресурсов, который управляет только одним ресурсом, то для управления ресурсами допустимо использовать деструктор.

- Понимать, что исключение, созданное в конструкторе базового класса, не может быть проглатываются в конструкторе производного класса. Если необходимо преобразовать и повторно создать исключение базового класса в производном конструкторе, используйте блок try функции.

- Определите, следует ли сохранять все состояния класса в члене данных, заключенном в интеллектуальный указатель, особенно если класс имеет концепцию "инициализация, которая может быть неудачной". Хотя C++ допускает неинициализированные элементы данных, он не поддерживает неинициализированные или частично инициализированные экземпляры класса. Конструктор должен быть успешно выполнен или завершился ошибкой. Если конструктор не выполняется до завершения, объект не создается.

- Не разрешать исключения в escape-последовательности из деструктора. Базовый аксиома C++ заключается в том, что деструкторы никогда не должны разрешать исключение для распространения стека вызовов. Если деструктор должен выполнить операцию, вызывающую исключение, он должен быть выполнен в блоке try catch и проглотить исключение. Стандартная библиотека обеспечивает эту гарантию для всех деструкторов, которые он определяет.

## <a name="see-also"></a>См. также раздел

[Современные рекомендации по C++ для исключений и обработки ошибок](errors-and-exception-handling-modern-cpp.md)<br/>
[Как взаимодействовать с исключительным и неисключительным кодом](how-to-interface-between-exceptional-and-non-exceptional-code.md)
