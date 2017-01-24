---
title: "&lt;memory&gt; | Microsoft Docs"
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
  - "memory/std::<memory>"
  - "std.<memory>"
  - "<memory>"
  - "std::<memory>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "memory - заголовок"
ms.assetid: ef8e38da-7c9d-4037-9ad1-20c99febf5dc
caps.latest.revision: 22
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;memory&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет класс, оператор и несколько шаблонов, позволяющих выделять и освобождать объекты.  
  
## Синтаксис  
  
```  
  
#include <memory>  
  
```  
  
## Участники  
  
### Функции  
  
|||  
|-|-|  
|[addressof](../Topic/addressof.md)|Получает истинный адрес объекта.|  
|[align](../Topic/align.md)|Возвращает указатель на диапазон заданного размера на основе указанного выравнивания и начального адреса.|  
|[allocate\_shared](../Topic/allocate_shared.md)|Создает `shared_ptr` для объектов, выделенных и созданных для заданного типа с указанным распределителем.|  
|[checked\_uninitialized\_copy](../misc/checked-uninitialized-copy.md)|То же, что и `uninitialized_copy`, но обеспечивает принудительное использование проверенного итератора в качестве итератора вывода.|  
|[checked\_uninitialized\_fill\_n](../misc/checked-uninitialized-fill-n.md)|То же, что и `uninitialized_fill_n`, но обеспечивает принудительное использование проверенного итератора в качестве итератора вывода.|  
|[const\_pointer\_cast](../Topic/const_pointer_cast.md)|Постоянное приведение к `shared_ptr`.|  
|[declare\_no\_pointers](../Topic/declare_no_pointers.md)|Сообщает сборщику мусора, что символы, начинающиеся с указанного адреса и попадающие в блок указанного размера, не содержат трассируемых указателей.|  
|[declare\_reachable](../Topic/declare_reachable.md)|Уведомляет сборщик мусора, что указанный адрес относится к выделенной памяти и является доступным.|  
|[default\_delete](../Topic/default_delete.md)|Удаляет объекты, выделенные с помощью `operator new`.  Подходит для использования с `unique_ptr`.|  
|[dynamic\_pointer\_cast](../Topic/dynamic_pointer_cast.md)|Динамическое приведение к `shared_ptr`.|  
|[get\_deleter](../Topic/get_deleter%20Function.md)|Получение метода удаления из `shared_ptr`.|  
|[get\_pointer\_safety](../Topic/get_pointer_safety.md)|Возвращает тип безопасности указателя, подразумеваемый любым сборщиком мусора.|  
|[get\_temporary\_buffer](../Topic/get_temporary_buffer.md)|Выделяет временное хранилище для последовательности элементов, которая не превышает заданное число элементов.|  
|[make\_shared](../Topic/make_shared%20\(%3Cmemory%3E\).md)|Создает и возвращает `shared_ptr`, указывающий на объект, для которого выделена память, созданный из нуля или нескольких аргументов с помощью распределителя по умолчанию.|  
|[make\_unique](../Topic/make_unique.md)|Создает и возвращает [unique\_ptr](../standard-library/unique-ptr-class.md), указывающий на объект, для которого выделена память, созданный из нуля или нескольких аргументов.|  
|[owner\_less](../Topic/owner_less.md)|Разрешает смешанные сравнения общих и слабых указателей на основе собственности.|  
|[pointer\_safety](../Topic/pointer_safety%20Enumeration.md)|Перечисление всех возможных возвращаемых значений для `get_pointer_safety`.|  
|[return\_temporary\_buffer](../Topic/return_temporary_buffer.md)|Отменяет выделение временной памяти, выделенной с помощью функции шаблона `get_temporary_buffer`.|  
|[static\_pointer\_cast](../Topic/static_pointer_cast.md)|Статическое приведение к `shared_ptr`.|  
|[swap](../Topic/swap%20\(C++%20Standard%20Library\).md)|Обмен двух объектов `shared_ptr` или `weak_ptr`.|  
|[unchecked\_uninitialized\_copy](../Topic/unchecked_uninitialized_copy.md)|То же, что и `uninitialized_copy`, но позволяет использовать непроверенный итератор как итератор вывода при определении \_SECURE\_SCL\=1.|  
|[unchecked\_uninitialized\_fill\_n](../misc/unchecked-uninitialized-fill-n.md)|То же, что и `uninitialized_fill_n`, но позволяет использовать непроверенный итератор как итератор вывода при определении \_SECURE\_SCL\=1.|  
|[undeclare\_no\_pointers](../Topic/undeclare_no_pointers.md)|Сообщает сборщику мусора, что символы в блоке памяти, определенном указателем на базовый адрес и размером блока, теперь могут содержать трассируемые указатели.|  
|[undeclare\_reachable](../Topic/undeclare_reachable.md)|Уведомляет `garbage_collector`, что указанная область памяти является недоступной.|  
|[uninitialized\_copy](../Topic/uninitialized_copy.md)|Копирует объекты из указанного входного диапазона в неинициализированный конечный диапазон.|  
|[uninitialized\_copy\_n](../Topic/uninitialized_copy_n.md)|Создает копию заданного числа элементов из итератора ввода.  Копии помещаются в прямой итератор.|  
|[uninitialized\_fill](../Topic/uninitialized_fill.md)|Копирует объекты с указанным значением в неинициализированный конечный диапазон.|  
|[uninitialized\_fill\_n](../Topic/uninitialized_fill_n.md)|Копирует объекты с указанным значением в указанное число элементов в неинициализированном конечном диапазоне.|  
  
### Операторы  
  
|||  
|-|-|  
|[operator\!\=](../Topic/operator!=%20\(%3Cmemory%3E\).md)|Проверяет на неравенство между объектами распределителя указанного класса.|  
|[operator\=\=](../Topic/operator==%20\(%3Cmemory%3E\).md)|Проверяет на равенство объекты распределителя указанного класса.|  
|[Оператор \>\=](../Topic/operator%3E=%20\(%3Cmemory%3E\).md)|Проверяет, является ли один объект распределителя больше или равным второму объекту распределителя указанного класса.|  
|[Оператор \<](../Topic/operator%3C%20\(%3Cmemory%3E\).md)|Проверяет, является ли один объект распределителя меньше или равным второму объекту распределителя указанного класса.|  
|[Оператор \<\=](../Topic/operator%3C=%20\(%3Cmemory%3E\).md)|Проверяет, является ли один объект меньше или равным второму объекту указанного класса.|  
|[Оператор \>](../Topic/operator%3E%20\(%3Cmemory%3E\).md)|Проверяет, является ли один объект больше второго объекта указанного класса.|  
|[\<\< \- оператор](../Topic/operator%3C%3C%20\(%3Cmemory%3E\).md)|Вставляет `shared_ptr`.|  
  
### Классы  
  
|||  
|-|-|  
|[allocator](../standard-library/allocator-class.md)|Класс шаблона описывает объект, который управляет выделением и освобождением памяти для массивов объектов типа **Тип**.|  
|[allocator\_traits](../Topic/allocator_traits%20Class.md)|Описывает объект, определяющий все сведения, необходимые контейнеру с распределителем.|  
|[auto\_ptr](../standard-library/auto-ptr-class.md)|Класс шаблона описывает объект, в котором хранится указатель на объект типа **Тип\***, для которого выделена память, гарантирующий, что объект, на который он указывает, удаляется при удалении входящего в его состав элемента auto\_ptr.|  
|[bad\_weak\_ptr](../standard-library/bad-weak-ptr-class.md)|Сообщает о необрабатываемом исключении weak\_ptr.|  
|[enabled\_shared\_from\_this](../standard-library/enable-shared-from-this-class.md)|Помогает сформировать `shared_ptr`.|  
|[pointer\_traits](../standard-library/pointer-traits-struct.md)|Предоставляет данные, необходимые объекту класса шаблонов `allocator_traits` для описания распределителя с типом указателя `Ptr`.|  
|[raw\_storage\_iterator](../Topic/raw_storage_iterator%20Class.md)|Класс\-адаптер, который предоставляется, чтобы алгоритмы могли сохранять свои результаты в неинициализированной памяти.|  
|[shared\_ptr](../standard-library/shared-ptr-class.md)|Помещает объект с динамическим выделением памяти в оболочку интеллектуального указателя с подсчитанными ссылками.|  
|[unique\_ptr](../standard-library/unique-ptr-class.md)|Хранит указатель на собственный объект.  Указатель не принадлежит никаким другим `unique_ptr`.  `unique_ptr` удаляется при удалении владельца.|  
|[weak\_ptr](../standard-library/weak-ptr-class.md)|Создает оболочку слабо связанного указателя.|  
  
### Специализации  
  
|||  
|-|-|  
|[allocator\<void\>](../standard-library/allocator-void-class.md)|Специализация распределителя класса шаблона для типа void, определяющая только типы членов, имеющие смысл в данном специализированном контексте.|  
  
## См. также  
 [Справочные материалы по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)