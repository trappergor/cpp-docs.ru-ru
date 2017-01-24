---
title: "Класс move_iterator | Microsoft Docs"
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
  - "std.move_iterator"
  - "move_iterator"
  - "iterator/std::move_iterator"
  - "std::move_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "move_iterator - класс"
ms.assetid: a5e5cdd8-a264-4c6b-9f9c-68b0e8edaab7
caps.latest.revision: 20
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс move_iterator
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Шаблон класса `move_iterator` является программой\-оболочкой для итератора.  Move\_iterator предоставляет то же поведение, что и инкапсулируемый в него \(хранящийся в нем\) итератор, за исключением того, что оператор разыменования хранящегося итератора превращается в ссылку rvalue, что превращает копирование в перемещение.  Дополнительные сведения о значениях rvalue см. в разделе [Декларатор ссылки Rvalue: &&](../cpp/rvalue-reference-declarator-amp-amp.md).  
  
## Синтаксис  
  
```  
template<class Iterator>  
    class move_iterator {  
public:  
    typedef Iterator iterator_type;  
    typedef typename      
        iterator_traits<Iterator>::iterator_category  
            iterator_category;  
    typedef typename iterator_traits<Iterator>::value_type  
        value_type;  
    typedef typename iterator_traits<Iterator>::difference_type  
        difference_type;  
    typedef Iterator  
        pointer;  
    typedef value_type&&  
        reference;  
  
    move_iterator();  
    explicit move_iterator (Iterator right);  
    template<class Type>  
        move_iterator (const move_iterator<Type>& right);  
    template <class Type>   
        move_iterator& operator=(const move_iterator<Type>& right);  
  
    iterator_type base () const;  
    reference operator* () const;  
    pointer operator-> () const;  
  
    move_iterator& operator++ ();  
    move_iterator operator++ (int);  
    move_iterator& operator-- ();  
    move_iterator operator-- (int);  
  
    move_iterator& operator+= (difference_type off);  
    move_iterator operator+ (difference_type off) const;  
    move_iterator& operator-= (difference_type off);  
    move_iterator operator- (difference_type off) const;  
    reference operator[] (difference_type off) const;  
    };  
```  
  
## Заметки  
 Класс шаблона описывает объект, поведение которого аналогично поведению итератора, кроме случаев, когда удаляется ссылка.  Он хранит итератор произвольного доступа типа `Iterator`, доступный посредством функции\-члена `base``()`.  Все операции с итератором `move_iterator` выполняются непосредственно в сохраненном итераторе, за исключением того, что результат `operator*` явным образом приводится к `value_type&&` для создания ссылки rvalue.  
  
 Итератор `move_iterator` может выполнять операции, не определенные инкапсулированным итератором.  Эти операции не следует использовать.  
  
### Конструкторы  
  
|||  
|-|-|  
|[move\_iterator](../Topic/move_iterator::move_iterator.md)|Конструктор для объектов типа `move_iterator`.|  
  
### Определения типов  
  
|||  
|-|-|  
|[move\_iterator::iterator\_type](../Topic/move_iterator::iterator_type.md)|Синоним параметра шаблона `RandomIterator`.|  
|[move\_iterator::iterator\_category](../Topic/move_iterator::iterator_category.md)|Синоним более длинного выражения `typename` с таким же именем, `iterator_category` определяет общие возможности данного итератора.|  
|[move\_iterator::value\_type](../Topic/move_iterator::value_type.md)|Синоним более длинного выражения `typename` с таким же именем, `value_type` описывает тип элементов итератора.|  
|[move\_iterator::difference\_type](../Topic/move_iterator::difference_type.md)|Синоним более длинного выражения `typename` с таким же именем, `difference_type` описывает целочисленный тип, необходимый для выражения разницы между элементами.|  
|[move\_iterator::pointer](../Topic/move_iterator::pointer.md)|Синоним параметра шаблона `RandomIterator`.|  
|[move\_iterator::reference](../Topic/move_iterator::reference.md)|Синоним ссылки `rvalue` `value_type&&`.|  
  
### Функции\-члены  
  
|||  
|-|-|  
|[move\_iterator::base](../Topic/move_iterator::base.md)|Функция\-член возвращает сохраненный итератор, инкапсулированный данным итератором `move_iterator`.|  
  
### Операторы  
  
|||  
|-|-|  
|[move\_iterator::operator\*](../Topic/move_iterator::operator*.md)|Возвращает `(reference)*``base``().`|  
|[move\_iterator::operator\+\+](../Topic/move_iterator::operator++.md)|Увеличивает значение сохраненного итератора.  Точное поведение определяется тем, является ли операция преинкрементной или постинкрементной.|  
|[move\_iterator::operator\-\-](../Topic/move_iterator::operator--.md)|Уменьшает значение сохраненного итератора.  Точное поведение определяется тем, является ли операция предекрементной или постдекрементной.|  
|[move\_iterator::operator\-\>](../Topic/move_iterator::operator-%3E.md)|Возвращает `&**this`.|  
|[move\_iterator::operator\-](../Topic/move_iterator::operator-.md)|Возвращает `move_iterator(*this) -=` путем вычитания правого значения из текущей позиции.|  
|[move\_iterator::operator](../Topic/move_iterator::operator.md)|Возвращает `(reference)*(*this + off)`.  Позволяет указать смещение с текущей базы для получения значения в этом местоположении.|  
|[move\_iterator::operator\+](../Topic/move_iterator::operator+.md)|Возвращает `move_iterator(*this) +=` значение.  Позволяет добавить смещение в текущую базу для получения значения в этом местоположении.|  
|[move\_iterator::operator\+\=](../Topic/move_iterator::operator+=.md)|Добавляет правое значение к сохраненному итератору и возвращает `*this`.|  
|[move\_iterator::operator\-\=](../Topic/move_iterator::operator-=.md)|Вычитает правое значение из сохраненного итератора и возвращает `*this`.|  
  
## Требования  
 **Заголовок:** \<iterator\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<iterator\>](../standard-library/iterator.md)   
 [Значения Lvalue и Rvalue](../Topic/Lvalues%20and%20Rvalues%20\(Visual%20C++\).md)   
 [Конструкторы move и операторы присваивания move \(C\+\+\)](../Topic/Move%20Constructors%20and%20Move%20Assignment%20Operators%20\(C++\).md)   
 [Библиотека стандартных шаблонов](../misc/standard-template-library.md)