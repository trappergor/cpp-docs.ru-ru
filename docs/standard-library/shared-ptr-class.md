---
title: "Класс shared_ptr | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "shared_ptr"
  - "tr1::shared_ptr"
  - "memory/std::tr1::shared_ptr"
  - "std::tr1::shared_ptr"
  - "std.tr1.shared_ptr"
  - "tr1.shared_ptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "shared_ptr - класс"
  - "shared_ptr - класс [TR1]"
ms.assetid: 1469fc51-c658-43f1-886c-f4530dd84860
caps.latest.revision: 29
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс shared_ptr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Помещает объект с динамическим выделением памяти в оболочку интеллектуального указателя с подсчитанными ссылками.  
  
## Синтаксис  
  
```  
template<class Ty>  
   class shared_ptr {  
public:  
    typedef Ty element_type;  
  
    shared_ptr();  
    shared_ptr(nullptr_t);   
    shared_ptr(const shared_ptr& sp);  
    shared_ptr(shared_ptr&& sp);  
    template<class Other>  
        explicit shared_ptr(Other * ptr);  
    template<class Other, class D>  
        shared_ptr(Other * ptr, D dtor);  
    template<class D>  
        shared_ptr(nullptr_t, D dtor);  
    template<class Other, class D, class A>  
        shared_ptr(Other *ptr, D dtor, A alloc);  
    template<class D, class A>  
        shared_ptr(nullptr_t, D dtor, A alloc);  
    template<class Other>  
        shared_ptr(const shared_ptr<Other>& sp);  
    template<class Other>  
        shared_ptr(const shared_ptr<Other>&& sp);  
    template<class Other>  
        explicit shared_ptr(const weak_ptr<Other>& wp);  
    template<class Other>  
        shared_ptr(auto_ptr<Other>& ap);  
    template<class Other, class D>  
        shared_ptr(unique_ptr<Other, D>&& up);  
    template<class Other>  
        shared_ptr(const shared_ptr<Other>& sp, Ty *ptr);  
    ~shared_ptr();  
    shared_ptr& operator=(const shared_ptr& sp);  
    template<class Other>   
        shared_ptr& operator=(const shared_ptr<Other>& sp);  
    shared_ptr& operator=(shared_ptr&& sp);  
    template<class Other>   
        shared_ptr& operator=(shared_ptr<Other>&& sp);  
    template<class Other>   
        shared_ptr& operator=(auto_ptr< Other >&& ap);  
    template <class Other, class D>   
        shared_ptr& operator=(const unique_ptr< Other, D>& up) = delete;  
    template <class Other, class D>  
        shared_ptr& operator=(unique_ptr<Other, D>&& up);  
    void swap(shared_ptr& sp);  
    void reset();  
    template<class Other>  
        void reset(Other *ptr);  
    template<class Other, class D>  
        void reset(Other *ptr, D dtor);  
    template<class Other, class D, class A>  
        void reset(Other *ptr, D dtor, A alloc);  
    Ty *get() const;  
    Ty& operator*() const;  
    Ty *operator->() const;  
    long use_count() const;  
    bool unique() const;  
    operator bool() const;  
  
    template<class Other>  
        bool owner_before(shared_ptr<Other> const& ptr) const;  
    template<class Other>  
        bool owner_before(weak_ptr<Other> const& ptr) const;  
    template<class D, class Ty>   
        D* get_deleter(shared_ptr<Ty> const& ptr);  
};  
  
```  
  
#### Параметры  
 `Ty`  
 Тип, управляемый общим указателем.  
  
 `Other`  
 Тип, управляемый указателем аргумента.  
  
 `ptr`  
 Копируемый указатель.  
  
 `D`  
 Тип метода удаления.  
  
 `A`  
 Тип распределителя.  
  
 `dtor`  
 Метод удаления.  
  
 `alloc`  
 Распределитель.  
  
 `sp`  
 Интеллектуальный указатель для копирования или перемещения.  
  
 `wp`  
 Слабый указатель для копирования или перемещения.  
  
 `ap`  
 Автоматический указатель для копирования или перемещения.  
  
 `up`  
 Уникальный указатель для перемещения.  
  
## Заметки  
 Класс шаблона описывает объект, который использует подсчет ссылок для управления ресурсами.  Объект `shared_ptr` фактически содержит указатель на ресурс, которым он владеет, или содержит пустой указатель \(NULL\).  Обладать ресурсом могут несколько объектов `shared_ptr`; при удалении последнего объекта `shared_ptr`, обладающего тем или иным ресурсом, данный ресурс освобождается.  
  
 `shared_ptr` прекращает владеть ресурсом при переназначении или сбросе.  
  
 Аргумент шаблона `Ty` может быть неполным типом, за исключением случаев, особо отмеченных для определенных функций\-членов.  
  
 При создании объекта `shared_ptr<Ty>` из указателя ресурса типа `G*` или из `shared_ptr<G>` тип указателя `G*` должен допускать преобразование в `Ty*`.  В противном случае код не будет компилироваться.  Пример:  
  
```cpp  
class F {};  
class G : public F {};  
```  
  
```cpp  
  
#include <memory>  
  
using namespace std;  
  
shared_ptr<G> sp0(new G);   // okay, template parameter G and argument G*  
shared_ptr<G> sp1(sp0);     // okay, template parameter G and argument shared_ptr<G>  
shared_ptr<F> sp2(new G);   // okay, G* convertible to F*  
shared_ptr<F> sp3(sp0);     // okay, template parameter F and argument shared_ptr<G>  
shared_ptr<F> sp4(sp2);     // okay, template parameter F and argument shared_ptr<F>  
shared_ptr<int> sp5(new G); // error, G* not convertible to int*  
shared_ptr<int> sp6(sp2);   // error, template parameter int and argument shared_ptr<F>  
```  
  
 Объект `shared_ptr` владеет ресурсом:  
  
-   если он был создан с использованием указателя на этот ресурс;  
  
-   если он был создан из объекта `shared_ptr`, владеющего этим ресурсом;  
  
-   если он был создан из объекта [Класс weak\_ptr](../standard-library/weak-ptr-class.md), указывающего на этот ресурс; либо  
  
-   если он был назначен владельцем этого ресурса при помощи [shared\_ptr::operator\=](../Topic/shared_ptr::operator=.md) или путем вызова функции\-члена [shared\_ptr::reset](../Topic/shared_ptr::reset.md).  
  
 Владеющие ресурсом объекты `shared_ptr` совместно используют один блок управления.  Блок управления содержит следующее:  
  
-   количество объектов `shared_ptr`, владеющих ресурсом;  
  
-   количество объектов `weak_ptr`, указывающих на ресурс;  
  
-   метод удаления для этого ресурса, если он есть;  
  
-   пользовательский распределитель для блока управления, если он есть.  
  
 Объект `shared_ptr`, инициализируемый при помощи пустого указателя, имеет блок управления и не является пустым.  После того как объект `shared_ptr` освобождает ресурс, он перестает быть его владельцем.  После того как объект `weak_ptr` освобождает ресурс, он перестает указывать на него.  
  
 Если количество объектов `shared_ptr`, владеющих ресурсом, становится равным нулю, ресурс освобождается путем удаления или передачи его адреса в метод удаления в зависимости от того, как изначально был создан владелец ресурса.  Если количество объектов `shared_ptr`, владеющих ресурсом, как и число объектов `weak_ptr`, которые указывают на ресурс, становится равным нулю, освобождается блок управления с использованием пользовательского распределителя этого блока управления при его наличии.  
  
 Пустой объект `shared_ptr` не владеет какими\-либо ресурсами и не имеет блока управления.  
  
 Метод удаления является объектом функции, имеющим функцию\-член `operator()`.  Его тип должен быть конструируемым по копии, а его конструктор копии и деструктор не должны выдавать исключения.  Он принимает один параметр — удаляемый объект.  
  
 Некоторые функции принимают список аргументов, определяющий свойства результирующего объекта `shared_ptr<Ty>` или `weak_ptr<Ty>`.  Такой список аргументов можно задать несколькими способами.  
  
 Нет аргументов — результирующий объект является пустым объектом `shared_ptr` или `weak_ptr`.  
  
 `ptr` — указатель типа `Other*` на ресурс, которым требуется управлять.  `Ty` должен быть полным типом.  Если функция завершается с ошибкой \(так как не удалось выделить блок управления\), он вычисляет выражение `delete ptr`.  
  
 `ptr, dtor` — указатель типа `Other*` на ресурс, которым требуется управлять, и метод удаления для данного ресурса.  Если функция завершается с ошибкой \(так как не удалось выделить блок управления\), он вызывает `dtor(ptr)`, который должен быть определен правильно.  
  
 `ptr, dtor, alloc` — указатель типа `Other*` на ресурс, которым требуется управлять, для управления, метод удаления для данного ресурса и распределитель для управления выделяемым и освобождаемым местом в хранилище.  Если функция завершается с ошибкой \(так как не удалось выделить блок управления\), он вызывает `dtor(ptr)`, который должен быть определен правильно.  
  
 `sp` — объект `shared_ptr<Other>`, владеющий ресурсом, которым требуется управлять.  
  
 `wp` — объект `weak_ptr<Other>`, указывающий на ресурс, которым требуется управлять.  
  
 `ap` — объект `auto_ptr<Other>`, содержащий указатель на ресурс, которым требуется управлять.  Если функция выполняется успешно, он вызывает `ap.release()`; в противном случае он выполняет выход из `ap` без изменений.  
  
 Во всех случаях тип указателя типа `Other*` должен допускать преобразование в `Ty*`.  
  
## Потокобезопасность  
 Несколько потоков могут одновременно считывать и записывать разные объекты `shared_ptr`, даже если они являются копиями с общим владельцем.  
  
## Участники  
  
### Конструкторы  
  
|||  
|-|-|  
|[shared\_ptr::shared\_ptr](../Topic/shared_ptr::shared_ptr.md)|Создает документ `shared_ptr`.|  
|[shared\_ptr::~shared\_ptr](../Topic/shared_ptr::~shared_ptr.md)|Удаляет `shared_ptr`.|  
  
### Методы  
  
|||  
|-|-|  
|[shared\_ptr::element\_type](../Topic/shared_ptr::element_type.md)|Тип элемента.|  
|[shared\_ptr::get](../Topic/shared_ptr::get.md)|Возвращает адрес принадлежащего ресурса.|  
|[shared\_ptr::owner\_before](../Topic/shared_ptr::owner_before.md)|Возвращает значение true, если `shared_ptr` упорядочен до \(меньше\) предоставленного указателя.|  
|[shared\_ptr::reset](../Topic/shared_ptr::reset.md)|Заменяет принадлежащий ресурс.|  
|[shared\_ptr::swap](../Topic/shared_ptr::swap.md)|Меняет местами два объекта `shared_ptr`.|  
|[shared\_ptr::unique](../Topic/shared_ptr::unique.md)|Проверяет, является ли принадлежащий ресурс уникальным.|  
|[shared\_ptr::use\_count](../Topic/shared_ptr::use_count.md)|Подсчитывает количество владельцев ресурса.|  
  
### Операторы  
  
|||  
|-|-|  
|[shared\_ptr::operator boolean\-type](../Topic/shared_ptr::operator%20boolean-type.md)|Проверяет существование принадлежащего ресурса.|  
|[shared\_ptr::operator\*](../Topic/shared_ptr::operator*.md)|Возвращает указанное значение.|  
|[shared\_ptr::operator\=](../Topic/shared_ptr::operator=.md)|Заменяет принадлежащий ресурс.|  
|[shared\_ptr::operator\-\>](../Topic/shared_ptr::operator-%3E.md)|Получает указатель на указанное значение.|  
  
## Требования  
 **Заголовок:** \<память\>  
  
 **Пространство имен:** std  
  
## См. также  
 [Класс weak\_ptr](../standard-library/weak-ptr-class.md)   
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)