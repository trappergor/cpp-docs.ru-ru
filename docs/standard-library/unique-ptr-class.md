---
title: "Класс unique_ptr | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "unique_ptr"
  - "std.unique_ptr"
  - "std::unique_ptr"
  - "memory/std::unique_ptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "unique_ptr - класс"
ms.assetid: acdf046b-831e-4a4a-83aa-6d4ee467db9a
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# Класс unique_ptr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Содержит указатель на собственный объект или массив.  Данный объект или массив не принадлежит никаким другим объектам `unique_ptr`.  Данный объект удаляется при удалении объекта `unique_ptr`.  
  
## Синтаксис  
  
```  
template< class T, class Del = default_delete<T> >  
    class unique_ptr {  
public:  
    unique_ptr( );  
    unique_ptr( nullptr_t Nptr );  
    explicit unique_ptr( pointer Ptr );  
    unique_ptr( pointer Ptr,  
        typename conditional<is_reference<Del>::value,   
            Del,  
            typename add_reference<const Del>::type>::type Deleter);  
    unique_ptr (pointer Ptr,  
        typename remove_reference<Del>::type&& Deleter);  
    unique_ptr (unique_ptr&& Right);  
    template<class T2, Class Del2> unique_ptr( unique_ptr<T2, Del2>&& Right );  
    unique_ptr( const unique_ptr& Right    ) = delete;  
    unique_ptr& operator=(const unique_ptr& Right     ) = delete;  
};  
  
```  
  
```  
//Specialization for arrays:  
template <class T, class D> class unique_ptr<T[], D>   
{   public:       
     typedef pointer;  
     typedef T element_type;  
     typedef D deleter_type;  
  
     constexpr unique_ptr() noexcept;  
     template <class U> explicit unique_ptr(U p) noexcept;  
     template <class U> unique_ptr(U p, see below d) noexcept;  
     template <class U> unique_ptr(U p, see below d) noexcept;  
     unique_ptr(unique_ptr&& u) noexcept;  
     constexpr unique_ptr(nullptr_t) noexcept : unique_ptr() { }  
     template <class U, class E>  
       unique_ptr(unique_ptr<U, E>&& u) noexcept;  
  
     ~unique_ptr();  
  
     unique_ptr& operator=(unique_ptr&& u) noexcept;  
     template <class U, class E>  
       unique_ptr& operator=(unique_ptr<U, E>&& u) noexcept;  
     unique_ptr& operator=(nullptr_t) noexcept;  
  
     T& operator[](size_t i) const;  
     pointer get() const noexcept;  
     deleter_type& get_deleter() noexcept;  
     const deleter_type& get_deleter() const noexcept;  
     explicit operator bool() const noexcept;  
  
     pointer release() noexcept;  
     void reset(pointer p = pointer()) noexcept;  
     void reset(nullptr_t = nullptr) noexcept;  
     template <class U> void reset(U p) noexcept = delete;  
     void swap(unique_ptr& u) noexcept;  
  
    // disable copy from lvalue  
     unique_ptr(const unique_ptr&) = delete;  
     unique_ptr& operator=(const unique_ptr&) = delete;  
   };  
 }  
  
```  
  
#### Параметры  
 `Right`  
 Объект `unique_ptr`.  
  
 `Nptr`  
 Интерфейс `rvalue` типа `std::nullptr_t`.  
  
 `Ptr`  
 Объект `pointer`.  
  
 `Deleter`  
 Функция `deleter`, которая привязана к `unique_ptr`.  
  
## Исключения  
 `unique_ptr` не генерирует исключения.  
  
## Заметки  
 Класс `unique_ptr` заменяет значение `auto_ptr` и может использоваться в качестве элемента контейнеров STL.  
  
 Используйте вспомогательную функцию [make\_unique](../Topic/make_unique.md) для создания новых экземпляров `unique_ptr`.  
  
 `unique_ptr` — единственное средство управления ресурсом.  Каждый объект `unique_ptr` сохраняет указатель на объект, которым обладает, или нулевой указатель.  Ресурс может принадлежать не более чем одному объекту `unique_ptr`;  в случае удаления объекта `unique_ptr`, которому принадлежит определенный ресурс, этот ресурс освобождается.  Объект `unique_ptr` можно перемещать, но нельзя копировать.  Дополнительные сведения см. в статье [Декларатор ссылки Rvalue: &&](../cpp/rvalue-reference-declarator-amp-amp.md).  
  
 Ресурс освобождается путем обращения к хранимому объекту `deleter` типа `Del`, которому известны принципы выделения ресурсов для конкретного объекта `unique_ptr`.  Значение по умолчанию `deleter` `default_delete``<T>` подразумевает, что ресурс, на который указывает `_Ptr`, выделяется при помощи `new` и может освобождаться путем обращения к `delete _``Ptr`.  \(Частичная специализация `unique_ptr<T[]>`управляет объектами массива, выделенными при помощи `new[]`, и обладает объектом `deleter` `default_delete<T[]>` по умолчанию для обращения к функции delete\[\] `_Ptr`.\)  
  
 Сохраненный указатель на принадлежащий ресурс, `stored_ptr` относится к типу `pointer`.  Он имеет значение `Del::pointer`, если определен, и значение `T *` , если не определен.  Сохраненный объект `deleter` `stored_deleter` не занимает пространство в объекте, если `deleter` не сохраняет данные о состоянии.  Обратите внимание, что `Del` может быть ссылочным типом.  
  
## Участники  
  
### Конструкторы  
  
|||  
|-|-|  
|[unique\_ptr::unique\_ptr](../Topic/unique_ptr::unique_ptr.md)|Для `unique_ptr` предусмотрено семь конструкторов.|  
  
### Typedefs  
  
|||  
|-|-|  
|[deleter\_type](../Topic/deleter_type.md)|Синоним параметра шаблона `Del`.|  
|[element\_type](../Topic/element_type.md)|Синоним для параметра шаблона `T``.`|  
|[указатель](../Topic/pointer.md)|Синоним для `Del::pointer`, если определен; в противном случае — значение `T *`.|  
  
### Функции\-члены  
  
|||  
|-|-|  
|[unique\_ptr::get](../Topic/unique_ptr::get.md)|Возвращает `stored_ptr`.|  
|[unique\_ptr::get\_deleter](../Topic/unique_ptr::get_deleter.md)|Возвращает ссылку на `stored_deleter`.|  
|[unique\_ptr::release](../Topic/unique_ptr::release.md)|сохраняет `pointer()` в `stored_ptr` и возвращает его предыдущее содержимое.|  
|[unique\_ptr::reset](../Topic/unique_ptr::reset.md)|Высвобождает текущий занятый ресурс и принимает новый ресурс.|  
|[unique\_ptr::swap](../Topic/unique_ptr::swap.md)|Выполняет обмен ресурса и `deleter` с указанным значением `unique_ptr`.|  
  
### Операторы  
  
|||  
|-|-|  
|`operator bool`|Оператор возвращает значение типа, которое можно преобразовать в значение `bool`.  Результат преобразования в `bool` — значение `true`, если `get() != pointer()`; в противном случае — значение `false`.|  
|`operator->`|Функция\-член возвращает значение `stored_ptr``.`|  
|`operator*`|Функция\-член возвращает значение\*`stored_ptr``.`|  
|[unique\_ptr operator\=](../Topic/unique_ptr%20operator=.md)|Присваивает значение `unique_ptr` \(или `pointer-type`\) текущему `unique_ptr`.|  
  
## Требования  
 **Заголовок:** \<memory\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<memory\>](../standard-library/memory.md)