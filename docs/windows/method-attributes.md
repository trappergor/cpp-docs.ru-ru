---
title: "Method Attributes | Microsoft Docs"
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
  - "method attributes"
  - "attributes [C++], reference topics"
ms.assetid: b2313352-480d-488b-8c35-6242ffd3a549
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Method Attributes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Следующие атрибуты применяются к методам в классе компонентном классе или интерфейсе.  
  
|Атрибут|Описание|  
|-------------|--------------|  
|[bindable](../windows/bindable.md)|Указывает, что свойство поддерживает привязку данных.|  
|[call\_as](../windows/call-as.md)|Включает функцию, не поддерживающие удаленное взаимодействие, сопоставляемый с удаленными функции.|  
|[custom](../windows/custom-cpp.md)|Позволяет указать собственный атрибут.|  
|[db\_column](../windows/db-column.md)|Привязывает указанный столбец в набор строк.|  
|[db\_command](../windows/db-command.md)|Создает команда OLE DB ".|  
|[db\_param](../windows/db-param.md)|Связывает указанная переменная члена с входом или параметром вывода и отделяет переменную.|  
|[db\_source](../windows/db-source.md)|Создает соединение с источником данных.|  
|[db\_table](../windows/db-table.md)|Открывает таблицу OLE DB.|  
|[defaultbind](../windows/defaultbind.md)|Отображает одно свойство, связываемое лучше всего представляет объект.|  
|[defaultcollelem](../windows/defaultcollelem.md)|Используется для оптимизации кода Visual Basic.|  
|[displaybind](../windows/displaybind.md)|Указывает свойство, которое должно отображаться пользователю как связываемая.|  
|[helpcontext](../windows/helpcontext.md)|Указывает идентификатор контекста, который позволяет пользователю просматривать сведения об этом элементе в файле Справки.|  
|[helpfile](../Topic/helpfile.md)|Задает имя файла Справки библиотеки типов.|  
|[helpstring](../windows/helpstring.md)|Задает символьную строку, используемую для описания элемента, к которому она применяется.|  
|[helpstringcontext](../windows/helpstringcontext.md)|Указывает идентификатор раздела в файле справки .hlp или .chm.|  
|[helpstringdll](../windows/helpstringdll.md)|Указывает имя dll\-библиотеки для использования выполнять поиск строки документа \(локализация\).|  
|[hidden](../Topic/hidden.md)|Показывает, что элемент существует, но не должен отображаться в обозревателе, ориентированном на пользователя.|  
|[id](../windows/id.md)|Указывает идентификатор DISPID для функции\-члена \(или свойство или метод в интерфейсе или диспетчерский интерфейс\).|  
|[immediatebind](../windows/immediatebind.md)|Показывает, что база данных будет уведомленна немедленно всех изменений к свойству данные\-привязанного объекта.|  
|[in](../Topic/in%20\(C++\).md)|Указывает, что параметр для передачи из вызывающей процедуры к вызываемой процедуре.|  
|[local](../windows/local-cpp.md)|Позволяет использовать компилятора MIDL как генератор заголовка при использовании в заголовке интерфейса.  При использовании в отдельной функции обозначает локальную процедуру, для которой нет заглушки не формируются.|  
|[nonbrowsable](../Topic/nonbrowsable.md)|Указывает, что член интерфейса не должен отображаться в обозревателе свойств.|  
|[propget](../windows/propget.md)|Определяет функции метода доступа свойства.|  
|[propput](../windows/propput.md)|Определяет функцию свойство\-параметра.|  
|[propputref](../windows/propputref.md)|Определяет функцию свойство\-параметра, которая использует ссылку вместо значения.|  
|[ptr](../windows/ptr.md)|Определяет указатель в виде полный указатель.|  
|[диапазон](../Topic/range%20\(C++\).md)|Определяет диапазон допустимых значений аргументов или полей, значения которых устанавливаются во время выполнения.|  
|[requestedit](../windows/requestedit.md)|Указывает, что свойство поддерживает инфраструктуру OnRequestEdit уведомление.|  
|[restricted](../windows/restricted.md)|Указывает, что член модуля, интерфейса или диспетчерский интерфейс не может вызываться произвольным образом.|  
|[satype](../windows/satype.md)|Указывает тип данных SAFEARRAY структура.|  
|[source](../Topic/source%20\(C++\).md)|Определяет интерфейсы источника элемента управления для точки подключения в классе.  В методе, свойстве или **источник** атрибут указывает на то, что участник получает объект или ВАРИАНТ, являющийся источником событий.|  
|[синхронизировать](../windows/synchronize.md)|Синхронизировать доступ к методу пристрелки.|  
|[vararg](../windows/vararg.md)|Указывает, что функция принимает переменное число аргументов.|  
  
## См. также  
 [Attributes by Usage](../windows/attributes-by-usage.md)