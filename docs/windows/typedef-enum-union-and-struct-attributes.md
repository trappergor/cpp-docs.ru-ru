---
title: "Typedef, Enum, Union, and Struct Attributes | Microsoft Docs"
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
  - "union attributes"
  - "attributes [C++], reference topics"
  - "struct attributes"
  - "typedef attributes"
  - "enum attributes"
ms.assetid: f8a4fe94-dc02-4aed-bc31-3e500d42f4c7
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Typedef, Enum, Union, and Struct Attributes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Следующие атрибуты применяются к [typedef](http://msdn.microsoft.com/ru-ru/cc96cf26-ba93-4179-951e-695d1f5fdcf1)"  [структура](../cpp/struct-cpp.md)и  [перечисления](../cpp/enumerations-cpp.md) ключевые слова C\+\+.  
  
### typedef  
  
|Атрибут|Описание|  
|-------------|--------------|  
|[case](../windows/case-cpp.md)|Используется с [switch\_type](../windows/switch-type.md) атрибут в выражении  **union**.|  
|[custom](../windows/custom-cpp.md)|Позволяет указать собственный атрибут.|  
|[export](../windows/export.md)|Структура данных будет располагаться в idl\-файле.|  
|[first\_is](../windows/first-is.md)|Определяет индекс первого элемента массива, которые необходимо передать.|  
|[helpcontext](../windows/helpcontext.md)|Указывает идентификатор контекста, который позволяет пользователю просматривать сведения об этом элементе в файле Справки.|  
|[helpfile](../Topic/helpfile.md)|Задает имя файла Справки библиотеки типов.|  
|[helpstring](../windows/helpstring.md)|Задает символьную строку, используемую для описания элемента, к которому она применяется.|  
|[library\_block](../windows/library-block.md)|Задает конструкцию внутри блока библиотеки файла idl.|  
|[ptr](../windows/ptr.md)|Определяет указатель в виде полный указатель.|  
|[public](../windows/public-cpp-attributes.md)|Гарантирует, что typedef переместится в библиотеку типов, несмотря на него нет ссылок из файла idl.|  
|[ref](../windows/ref-cpp.md)|Задает указатель ссылки.|  
|[switch\_is](../windows/switch-is.md)|Определяет выражение или идентификатор, используемый как соединение дискриминантное, которое выбирает член объединения.|  
|[switch\_type](../windows/switch-type.md)|Указывает тип переменной, используемой в качестве соединение дискриминантное.|  
|[unique](../windows/unique-cpp.md)|Задает уникальный указатель.|  
|[wire\_marshal](../windows/wire-marshal.md)|Определяет тип данных, который будет использоваться для передачи конкретного приложения вместо этого типа данных.|  
  
### enum  
  
|Атрибут|Описание|  
|-------------|--------------|  
|[custom](../windows/custom-cpp.md)|Позволяет указать собственный атрибут.|  
|[export](../windows/export.md)|Структура данных будет располагаться в idl\-файле.|  
|[uuid](../windows/uuid-cpp-attributes.md)|Указывает уникальный идентификатор класса или интерфейса.|  
|[v1\_enum](../windows/v1-enum.md)|Указывает, что заданный перечислимый тип был передан в качестве 32 сущность, а не 16\-разрядное значение по умолчанию.|  
  
### union  
  
|Атрибут|Описание|  
|-------------|--------------|  
|[custom](../windows/custom-cpp.md)|Позволяет указать собственный атрибут.|  
|[export](../windows/export.md)|Структура данных будет располагаться в idl\-файле.|  
|[first\_is](../windows/first-is.md)|Определяет индекс первого элемента массива, которые необходимо передать.|  
|[last\_is](../windows/last-is.md)|Определяет индекс последнего элемента в массиве для отправки.|  
|[length\_is](../windows/length-is.md)|Определяет количество элементов массива, которые необходимо передать.|  
|[max\_is](../windows/max-is.md)|Показывает максимальное допустимое значение для индекса массива.|  
|[size\_is](../Topic/size_is.md)|Определяет размер памяти, выделенной для указанных размеров указателей, заданные размеры указателей на указанным размером и указателям, single или многомерным таблицам.|  
|[unique](../windows/unique-cpp.md)|Задает уникальный указатель.|  
|[uuid](../windows/uuid-cpp-attributes.md)|Указывает уникальный идентификатор класса или интерфейса.|  
  
### Соединение Nonencapsulated  
  
|Атрибут|Описание|  
|-------------|--------------|  
|[ms\_union](../windows/ms-union.md)|Контролирует выравнивание представлений сведениям о сети nonencapsulated соединений.|  
|[no\_injected\_text](../windows/no-injected-text.md)|Запрещает компилятору впрыскивать код в результате использования атрибута.|  
  
### struct  
  
|Атрибут|Описание|  
|-------------|--------------|  
|[aggregatable](../Topic/aggregatable.md)|Указывает, что класс поддерживает агрегирование.|  
|[агрегаты](../windows/aggregates.md)|Указывает, что элемент управления выполняет статистическую обработку класс целевого объекта.|  
|[appobject](../Topic/appobject.md)|Определяет coclass, как объект приложения, который связан с полным приложением exe, и указывает на то, что функции и свойства coclass глобально доступны в этой библиотеке типов.|  
|[CoClass](../windows/coclass.md)|Создает элемент управления ActiveX.|  
|[com\_interface\_entry](../Topic/com_interface_entry%20\(C++\).md)|Добавляет запись интерфейса для сопоставления модели COM.|  
|[Элемент управления](../windows/control.md)|Указывает, что пользовательский тип элемента управления.|  
|[custom](../windows/custom-cpp.md)|Позволяет указать собственный атрибут.|  
|[db\_column](../windows/db-column.md)|Привязывает указанный столбец в набор строк.|  
|[db\_command](../windows/db-command.md)|Создает команда OLE DB ".|  
|[db\_param](../windows/db-param.md)|Связывает указанная переменная члена с входом или параметром вывода и отделяет переменную.|  
|[db\_source](../windows/db-source.md)|Создает соединение с источником данных.|  
|[db\_table](../windows/db-table.md)|Открывает таблицу OLE DB.|  
|[default](../windows/default-cpp.md)|Указывает, что пользовательская или диспетчерский интерфейс, определенные в компонентном классе представляют по умолчанию интерфейса программирования.|  
|[defaultvtable](../windows/defaultvtable.md)|Определяет интерфейс, например по умолчанию vtable интерфейс для элемента управления.|  
|[event\_receiver](../windows/event-receiver.md)|Создает приемник событий.|  
|[event\_source](../windows/event-source.md)|Создает источник события.|  
|[export](../windows/export.md)|Структура данных будет располагаться в idl\-файле.|  
|[first\_is](../windows/first-is.md)|Определяет индекс первого элемента массива, которые необходимо передать.|  
|[hidden](../Topic/hidden.md)|Показывает, что элемент существует, но не должен отображаться в обозревателе, ориентированном на пользователя.|  
|[implements\_category](../Topic/implements_category.md)|Указывает реализации категории компонентов для класса.|  
|[last\_is](../windows/last-is.md)|Определяет индекс последнего элемента в массиве для отправки.|  
|[length\_is](../windows/length-is.md)|Определяет количество элементов массива, которые необходимо передать.|  
|[max\_is](../windows/max-is.md)|Показывает максимальное допустимое значение для индекса массива.|  
|[requires\_category](../windows/requires-category.md)|Определяет категории необходимого компонента класса целевого объекта.|  
|[size\_is](../Topic/size_is.md)|Определяет размер памяти, выделенной для указанных размеров указателей, заданные размеры указателей на указанным размером и указателям, single или многомерным таблицам.|  
|[source](../Topic/source%20\(C++\).md)|В классе определяет интерфейсы источника com\-объекта для точки подключения.  Свойства или метода, указывает, что член или ВАРИАНТ возвращает объект, являющийся источником событий.|  
|[Потоки](../windows/threading-cpp.md)|Указывает потоковую модель для com\-объекта.|  
|[unique](../windows/unique-cpp.md)|Задает уникальный указатель.|  
|[uuid](../windows/uuid-cpp-attributes.md)|Указывает уникальный идентификатор класса или интерфейса.|  
|[версия](../windows/version-cpp.md)|Определяет конкретную версию среди нескольких версий класса.|  
|[vi\_progid](../windows/vi-progid.md)|Определяет версия\-независимую форму программного идентификатора.|  
  
## См. также  
 [Attributes by Usage](../windows/attributes-by-usage.md)