---
title: "Класс insert_iterator | Microsoft Docs"
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
  - "std::insert_iterator"
  - "iterator/std::insert_iterator"
  - "std.insert_iterator"
  - "insert_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "insert_iterator - класс"
  - "insert_iterator - класс, синтаксис"
ms.assetid: d5d86405-872e-4e3b-9e68-c69a2b7e8221
caps.latest.revision: 17
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс insert_iterator
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Описывает адаптер итератора, удовлетворяющий требованиям итератора вывода.  Вставляет, а не перезаписывает элементы в последовательность, тем самым предоставляя семантику, отличную от семантики перезаписи, предоставляемой итераторами контейнеров последовательности и ассоциативных контейнеров C\+\+.  Класс `insert_iterator` шаблонизируется в адаптируемом типе контейнера.  
  
## Синтаксис  
  
```  
template <class Container> class insert_iterator;  
```  
  
#### Параметры  
 `Container`  
 Тип контейнера, в который итератор `insert_iterator` вставит элементы.  
  
## Заметки  
 Контейнер типа **Container** должен удовлетворять требованиям к контейнеру переменного размера и обладать функцией\-членом вставки с двумя аргументами, параметры которой относятся к типам **Container::iterator** и **Container::value\_type**, возвращающей тип **Container::iterator**.  Последовательность библиотеки стандартных шаблонов и упорядоченные ассоциативные контейнеры удовлетворяют данным требованиям и могут быть адаптированы к использованию в сочетании с итераторами `insert_iterator`.  Для ассоциативных контейнеров аргумент позиции обрабатывается как подсказка, которая потенциально может увеличить или снизить производительность в зависимости от эффективности подсказки.  Итератор `insert_iterator` всегда необходимо инициализировать с его контейнером.  
  
### Конструкторы  
  
|||  
|-|-|  
|[insert\_iterator](../Topic/insert_iterator::insert_iterator.md)|Создает итератор `insert_iterator`, добавляющий элемент в указанную позицию в контейнере.|  
  
### Определения типов  
  
|||  
|-|-|  
|[container\_type](../Topic/insert_iterator::container_type.md)|Тип, представляющий контейнер, в который будет осуществляться вставка общего типа.|  
|[reference](../Topic/insert_iterator::reference.md)|Тип, который предоставляет ссылку на элемент последовательности под управлением связанного контейнера.|  
  
### Операторы  
  
|||  
|-|-|  
|[operator\*](../Topic/insert_iterator::operator*.md)|Оператор удаления ссылки, используемый для применения выражения итератора вывода \*`i` \= `x` для вставки общего типа.|  
|[operator\+\+](../Topic/insert_iterator::operator++.md)|Увеличивает `insert_iterator` до следующего местоположения, в котором можно сохранить значение.|  
|[operator\=](../Topic/insert_iterator::operator=.md)|Оператор присваивания, используемый для применения выражения итератора вывода \*`i` \= `x` для вставки общего типа.|  
  
## Требования  
 **Заголовок:** \<iterator\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<iterator\>](../standard-library/iterator.md)   
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Библиотека стандартных шаблонов](../misc/standard-template-library.md)