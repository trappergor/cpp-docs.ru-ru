---
title: "Class Attributes | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "attributes [C++], class attributes"
  - "class attributes"
ms.assetid: fad04ea1-d8ff-46d4-bb42-2b4500a6ab60
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Class Attributes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Следующие атрибуты применяются к [класс](../cpp/class-cpp.md) ключевое слово C\+\+.  
  
|Атрибут|Описание|  
|-------------|--------------|  
|[aggregatable](../Topic/aggregatable.md)|Указывает, что класс поддерживает агрегирование.|  
|[агрегаты](../windows/aggregates.md)|Указывает, что элемент управления выполняет статистическую обработку класс целевого объекта.|  
|[appobject](../Topic/appobject.md)|Определяет coclass, как объект приложения, который связан с полным приложением exe, и указывает на то, что функции и свойства coclass глобально доступны в этой библиотеке типов.|  
|[case](../windows/case-cpp.md)|Используется с [switch\_type](../windows/switch-type.md) атрибут в соединении.|  
|[CoClass](../windows/coclass.md)|Создает элемент управления ActiveX.|  
|[com\_interface\_entry](../Topic/com_interface_entry%20\(C++\).md)|Добавляет запись интерфейса для сопоставления модели COM.|  
|[Элемент управления](../windows/control.md)|Указывает, что пользовательский тип элемента управления.|  
|[custom](../windows/custom-cpp.md)|Позволяет указать собственный атрибут.|  
|[db\_command](../windows/db-command.md)|Создает команда OLE DB ".|  
|[db\_param](../windows/db-param.md)|Связывает указанная переменная члена с входом или параметром вывода и отделяет переменную.|  
|[db\_source](../windows/db-source.md)|Создает соединение с источником данных.|  
|[db\_table](../windows/db-table.md)|Открывает таблицу OLE DB.|  
|[default](../windows/default-cpp.md)|Указывает, что пользовательская или диспетчерский интерфейс, определенные в компонентном классе представляют по умолчанию интерфейса программирования.|  
|[defaultvtable](../windows/defaultvtable.md)|Определяет интерфейс, например по умолчанию vtable интерфейс для элемента управления.|  
|[event\_receiver](../windows/event-receiver.md)|Создает приемник событий.|  
|[event\_source](../windows/event-source.md)|Создает источник события.|  
|[helpcontext](../windows/helpcontext.md)|Указывает идентификатор контекста, который позволяет пользователю просматривать сведения об этом элементе в файле Справки.|  
|[helpfile](../Topic/helpfile.md)|Задает имя файла Справки библиотеки типов.|  
|[helpstringcontext](../windows/helpstringcontext.md)|Указывает идентификатор раздела в файле справки .hlp или .chm.|  
|[helpstring](../windows/helpstring.md)|Задает символьную строку, используемую для описания элемента, к которому она применяется.|  
|[hidden](../Topic/hidden.md)|Показывает, что элемент существует, но не должен отображаться в обозревателе, ориентированном на пользователя.|  
|[implements](../Topic/implements%20\(C++\).md)|Определяет интерфейсы диспетчеризации, принуждаются, чтобы быть членами компонентного класса IDL.|  
|[implements\_category](../Topic/implements_category.md)|Указывает реализации категории компонентов для класса.|  
|[модуль](../windows/module-cpp.md)|Указывает блок библиотеки в idl\-файле.|  
|[noncreatable](../windows/noncreatable.md)|Определяет объект, который не может быть создан самостоятельно.|  
|[идентификатор progid](../Topic/progid.md)|Указывает идентификатор progid элемента управления.|  
|[registration\_script](../windows/registration-script.md)|Выполняет указанный скрипт регистрации.|  
|[requestedit](../windows/requestedit.md)|Указывает, что свойство поддерживает инфраструктуру OnRequestEdit уведомление.|  
|[source](../Topic/source%20\(C++\).md)|Определяет интерфейсы источника элемента управления для точки подключения в классе.  В методе, свойстве или **источник** атрибут указывает на то, что участник получает объект или ВАРИАНТ, являющийся источником событий.|  
|[support\_error\_information](../windows/support-error-info.md)|Поддерживает отчеты об ошибках для целевого объекта.|  
|[Потоки](../windows/threading-cpp.md)|Указывает потоковую модель для элемента управления.|  
|[uuid](../windows/uuid-cpp-attributes.md)|Указывает уникальный идентификатор класса или интерфейса.|  
|[версия](../windows/version-cpp.md)|Определяет конкретную версию среди нескольких версий класса.|  
|[vi\_progid](../windows/vi-progid.md)|Определяет версия\-независимую форму программного идентификатора.|  
  
## См. также  
 [Attributes by Usage](../windows/attributes-by-usage.md)