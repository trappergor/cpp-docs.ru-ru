---
title: "Класс weak_ptr | Microsoft Docs"
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
  - "std.tr1.weak_ptr"
  - "tr1.weak_ptr"
  - "weak_ptr"
  - "tr1::weak_ptr"
  - "std::tr1::weak_ptr"
  - "memory/std::tr1::weak_ptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "weak_ptr - класс"
  - "weak_ptr - класс [TR1]"
ms.assetid: 2db4afb2-c7be-46fc-9c20-34ec2f8cc7c2
caps.latest.revision: 22
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс weak_ptr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Создает оболочку слабо связанного указателя.  
  
## Синтаксис  
  
```  
template<class Ty> class weak_ptr {  
public:  
    typedef Ty element_type;  
  
    weak_ptr();  
    weak_ptr(const weak_ptr&);  
    template<class Other>  
        weak_ptr(const weak_ptr<Other>&);  
    template<class Other>  
        weak_ptr(const shared_ptr<Other>&);  
  
    weak_ptr& operator=(const weak_ptr&);  
    template<class Other>  
        weak_ptr& operator=(const weak_ptr<Other>&);  
    template<class Other>  
        weak_ptr& operator=(shared_ptr<Other>&);  
  
    void swap(weak_ptr&);  
    void reset();  
  
    long use_count() const;  
    bool expired() const;  
    shared_ptr<Ty> lock() const;  
    };  
```  
  
#### Параметры  
 `Ty`  
 Тип, управляемый слабым указателем.  
  
## Заметки  
 Класс шаблона описывает объект, который указывает на ресурс, управляемый одним или несколькими объектами [Класс shared\_ptr](../standard-library/shared-ptr-class.md).  Объекты `weak_ptr`, которые указывают на ресурс, не влияют на количество ссылок на ресурс.  Таким образом, когда последний объект `shared_ptr`, который управляет этим ресурсом, будет уничтожен, ресурс освободится, даже если существуют объекты `weak_ptr`, указывающие на этот ресурс.  Это важно, чтобы избежать циклов в структурах данных.  
  
 Объект `weak_ptr` указывает на ресурс, если он был создан из объекта `shared_ptr`, который владеет этим ресурсом, если он был создан из объекта `weak_ptr`, который указывает на этот ресурс или если этот ресурс был назначен ему с помощью [weak\_ptr::operator\=](../Topic/weak_ptr::operator=.md).  Объект `weak_ptr` не предоставляет прямой доступ к ресурсу, на который он указывает.  Код, которому необходимо использовать ресурс, делает с это с помощью объекта `shared_ptr`, который владеет этим ресурсом, который создается функцией\-членом [weak\_ptr::lock](../Topic/weak_ptr::lock.md).  Срок действия объекта `weak_ptr` истекает, если ресурс, на который он указывает, был освобожден, так как все объекты `shared_ptr`, владеющие ресурсом, были уничтожены.  Вызов `lock` в объекте `weak_ptr` с истекшим сроком действия создает пустой объект shared\_ptr.  
  
 Пустой объект weak\_ptr не указывает на какие\-либо ресурсы и не содержит блок управления.  Его функция\-член `lock` возвращает пустой объект shared\_ptr.  
  
 Цикл происходит, если два или более ресурсов, управляемых объектами `shared_ptr` содержат ссылающиеся друг на друга объекты `shared_ptr`.  Например, цикличный связанный список с тремя элементами содержит головной узел `N0`; этот узел включает объект `shared_ptr`, который владеет следующим узлом, `N1`; этот узел содержит объект `shared_ptr`, который владеет следующим узлом, `N2`; этот узел, в свою очередь, содержит объект `shared_ptr`, который владеет головным узлом `N0`, что создает цикл.  В этой ситуации ни один из счетчиков ссылок не станет нулем, а узлы в цикле не будут освобождены.  Чтобы исключить цикл, последний узел `N2` должен содержать объект `weak_ptr`, указывающий на `N0`, а не объект `shared_ptr`.  Так как объект `weak_ptr` не владеет `N0`, он не влияет на количество ссылок `N0`, а при уничтожении последней ссылки программы на головной узел узлы в списке также будут уничтожены.  
  
## Участники  
  
### Конструкторы  
  
|||  
|-|-|  
|[weak\_ptr::weak\_ptr](../Topic/weak_ptr::weak_ptr.md)|Создает документ `weak_ptr`.|  
  
### Методы  
  
|||  
|-|-|  
|[weak\_ptr::element\_type](../Topic/weak_ptr::element_type.md)|Тип элемента.|  
|[weak\_ptr::expired](../Topic/weak_ptr::expired.md)|Проверяет, истек ли срок действия владения.|  
|[weak\_ptr::lock](../Topic/weak_ptr::lock.md)|Получает эксклюзивные права владения ресурсом.|  
|[weak\_ptr::owner\_before](../Topic/weak_ptr::owner_before.md)|Возвращает `true`, если этот объект `weak_ptr` заказывался раньше заданного указателя \(или меньше него\).|  
|[weak\_ptr::reset](../Topic/weak_ptr::reset.md)|Освобождает ресурс, которым владеет.|  
|[weak\_ptr::swap](../Topic/weak_ptr::swap.md)|Меняет местами два объекта `weak_ptr`.|  
|[weak\_ptr::use\_count](../Topic/weak_ptr::use_count.md)|Считает количество назначенных объектов `shared_ptr`.|  
  
### Операторы  
  
|||  
|-|-|  
|[weak\_ptr::operator\=](../Topic/weak_ptr::operator=.md)|Заменяет ресурс, которым владеет.|  
  
## Требования  
 **Заголовок:** \<память\>  
  
 **Пространство имен:** std  
  
## См. также  
 [Класс shared\_ptr](../standard-library/shared-ptr-class.md)