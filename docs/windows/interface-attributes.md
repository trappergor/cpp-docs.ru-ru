---
title: "Interface Attributes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "attributes [C++], reference topics"
  - "interface attributes"
ms.assetid: 27fcdfee-abce-4585-8b53-ee31635356e8
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Interface Attributes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Следующие атрибуты применяются к [интерфейс \(или \_\_interface\)](../Topic/__interface.md) ключевое слово C\+\+.  
  
|Атрибут|Описание|  
|-------------|--------------|  
|[async\_uuid](../Topic/async_uuid.md)|Определяет UUID, инструктирует компилятор MIDL задаются и синхронные и асинхронные версии интерфейсов модели COM.|  
|[custom](../windows/custom-cpp.md)|Позволяет определить собственные атрибуты.|  
|[dispinterface](../windows/dispinterface.md)|Задает интерфейс в файле idl как интерфейс диспетчеризации.|  
|[dual](../Topic/dual.md)|Задает интерфейс в файле idl как сдвоенный интерфейс.|  
|[export](../windows/export.md)|Структура данных будет располагаться в idl\-файле.|  
|[helpcontext](../windows/helpcontext.md)|Указывает идентификатор контекста, который позволяет пользователю просматривать сведения об этом элементе в файле Справки.|  
|[helpfile](../Topic/helpfile.md)|Задает имя файла Справки библиотеки типов.|  
|[helpstring](../windows/helpstring.md)|Задает символьную строку, используемую для описания элемента, к которому она применяется.|  
|[helpstringcontext](../windows/helpstringcontext.md)|Указывает идентификатор раздела в файле справки .hlp или .chm.|  
|[helpstringdll](../windows/helpstringdll.md)|Указывает имя dll\-библиотеки для использования выполнять поиск строки документа \(локализация\).|  
|[hidden](../Topic/hidden.md)|Показывает, что элемент существует, но не должен отображаться в обозревателе, ориентированном на пользователя.|  
|[library\_block](../windows/library-block.md)|Задает конструкцию внутри блока библиотеки файла idl.|  
|[local](../windows/local-cpp.md)|Позволяет использовать компилятора MIDL как генератор заголовка при использовании в заголовке интерфейса.  При использовании в отдельной функции обозначает локальную процедуру, для которой нет заглушки не формируются.|  
|[nonextensible](../Topic/nonextensible.md)|Указывает, что `IDispatch` реализация включает только перечисленные свойства и методы в описании интерфейса и не может быть удлинена с дополнительными элементами во время выполнения.  Этот атрибут допустим только на a [Двойной](../Topic/dual.md) интерфейс.|  
|[odl](../windows/odl.md)|Задает интерфейс в качестве интерфейса на языке описания объектов \(ODL\).|  
|[Объект.](../Topic/object%20\(C++\).md)|Определяет пользовательский интерфейс.|  
|[oleautomation](../windows/oleautomation.md)|Указывает, что интерфейс совместимый с автоматизацией.|  
|[pointer\_default](../windows/pointer-default.md)|Определяет атрибут по умолчанию указателя для всех указателей, отличный от верхнего уровня указатели, отображаемые в списки параметров.|  
|[ptr](../windows/ptr.md)|Определяет указатель в виде полный указатель.|  
|[restricted](../windows/restricted.md)|Означают, члены библиотек не может вызываться произвольным образом.|  
|[uuid](../windows/uuid-cpp-attributes.md)|Предоставляет уникальный идентификатор для библиотеки|  
  
 Необходимо соблюдать следующие правила для определения интерфейса:  
  
-   Соглашение о вызовах по умолчанию \_\_stdcall.  
  
-   Идентификатор GUID указан, если не указывать.  
  
-   Нет перегруженные методы не допускаются.  
  
 Если определение UUID создается атрибут и использованием того же имени интерфейса в другом атрибуте проектов, один и тот же идентификатор GUID.  
  
## См. также  
 [Attributes by Usage](../windows/attributes-by-usage.md)