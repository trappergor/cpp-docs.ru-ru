---
title: "Класс auto_ptr | Microsoft Docs"
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
  - "std::auto_ptr"
  - "std.auto_ptr"
  - "auto_ptr"
  - "memory/std::auto_ptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto_ptr - класс"
ms.assetid: 7f9108b6-9eb3-4634-b615-cf7aa814f23b
caps.latest.revision: 26
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс auto_ptr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Заключает в оболочку интеллектуальный указатель вокруг ресурса, что гарантирует, что ресурс будет удален автоматически, когда точка управления выходит за пределы блока.  
  
 Более мощный класс `unique_ptr` имеет более высокий приоритет, чем `auto_ptr`.  Дополнительные сведения см. в статье [Класс unique\_ptr](../standard-library/unique-ptr-class.md).  
  
 Дополнительные сведения о `throw()` и об обработке исключений см. в статье [Спецификации исключений \(throw\)](../cpp/exception-specifications-throw-cpp.md).  
  
## Синтаксис  
  
```  
template<class Type>  
    class auto_ptr {  
public:  
    typedef Type element_type;  
    explicit auto_ptr(Type *_Ptr = 0) throw();  
    auto_ptr(auto_ptr<Type>& _Right) throw();  
    template<class Other>  
        operator auto_ptr<Other>() throw();  
    template<class Other>  
        auto_ptr<Type>& operator=(auto_ptr<Other>& _Right) throw();  
    template<class Other>  
        auto_ptr(auto_ptr<Other>& _Right);  
    auto_ptr<Type>& operator=(auto_ptr<Type>& _Right);  
    ~auto_ptr();  
    Type& operator*() const throw();  
    Type *operator->()const throw();  
    Type *get() const throw();  
    Type *release()throw();  
    void reset(Type *_Ptr = 0);  
};  
```  
  
#### Параметры  
 `_Right`  
 `auto_ptr`, из которого необходимо получить существующий ресурс.  
  
 `_Ptr`  
 Указатель, указанный для замены сохраненного указателя.  
  
## Заметки  
 Этот класс шаблона описывает интеллектуальный указатель, который называется `auto_ptr,`, на выделенный объект.  Указатель должен быть пустым или должен обозначать объект, выделенный `new`.  `auto_ptr` передает право владения, если сохраненное значение присваивается другому объекту  \(сохраненное значение заменяется после перемещения с пустым указателем\). Деструктор `auto_ptr<Type>` удаляет выделенный объект.  `auto_ptr<Type>` гарантирует, что выделенный объект автоматически удаляется при выходе точки управления за пределы блока даже с использованием созданного исключения.  Не следует создавать два объекта `auto_ptr<Type>`, владеющих одним объектом.  
  
 Вы можете передать объект `auto_ptr<Type>` по значению в виде аргумента в вызове функции.  `auto_ptr` не может быть элементом любого контейнера стандартной библиотеки.  Невозможно надежно управлять последовательностью объектов `auto_ptr<Type>` с помощью контейнера библиотеки стандартных шаблонов.  
  
## Участники  
  
### Конструкторы  
  
|||  
|-|-|  
|[auto\_ptr](../Topic/auto_ptr::auto_ptr.md)|Конструктор для объектов типа `auto_ptr`.|  
  
### Typedefs  
  
|||  
|-|-|  
|[element\_type](../Topic/auto_ptr::element_type.md)|Этот тип является синонимом для параметра шаблона `Type`.|  
  
### Функции\-члены  
  
|||  
|-|-|  
|[get](../Topic/auto_ptr::get.md)|Эта функция\-член возвращает сохраненный указатель `myptr`.|  
|[выпуск](../Topic/auto_ptr::release.md)|Этот член заменяет сохраненный указатель `myptr` на пустой указатель и возвращает сохраненный ранее указатель.|  
|[сброс](../Topic/auto_ptr::reset.md)|Эта функция\-член вычисляет выражение `delete myptr`, но только если значение сохраненного указателя `myptr` изменяется после вызова функции.  Затем она заменяет сохраненный указатель на `ptr`.|  
  
### Операторы  
  
|||  
|-|-|  
|[operator \=](../Topic/auto_ptr::operator=.md)|Оператор присваивания, который передает право владения от одного объекта `auto_ptr` другому.|  
|[operator\*](../Topic/auto_ptr::operator*.md)|Оператор удаления ссылки для объектов типа `auto_ptr`.|  
|[operator\-\>](../Topic/auto_ptr::operator-%3E.md)|Оператор для разрешения доступа к членам.|  
|[operator auto\_ptr\<Other\>](../Topic/auto_ptr::operator%20auto_ptr%3COther%3E.md)|Приводит из одного вида `auto_ptr` в другой вид `auto_ptr`.|  
|[operator auto\_ptr\_ref\<Other\>](../Topic/auto_ptr::operator%20auto_ptr_ref%3COther%3E.md)|Приводит из `auto_ptr` в `auto_ptr_ref`.|  
  
## Требования  
 **Заголовок:** \<memory\>  
  
 **Пространство имен:** std  
  
## См. также  
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Класс unique\_ptr](../standard-library/unique-ptr-class.md)