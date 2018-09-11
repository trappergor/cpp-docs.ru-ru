---
title: Атрибуты метода | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- method attributes
- attributes [C++/CLI], reference topics
ms.assetid: b2313352-480d-488b-8c35-6242ffd3a549
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 27540db2da7aecbe7a4b70b786bbf05bf608e889
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44317437"
---
# <a name="method-attributes"></a>Атрибуты метода

Следующие атрибуты применяются к методам в классе, компонентный класс или интерфейс.

|Атрибут|Описание|
|---------------|-----------------|
|[bindable](../windows/bindable.md)|Указывает, что свойство поддерживает привязку данных.|
|[call_as](../windows/call-as.md)|Позволяет сопоставить с удаленной функции функции не поддерживающие удаленное взаимодействие.|
|[Custom](../windows/custom-cpp.md)|Позволяет определять собственный атрибут.|
|[db_column](../windows/db-column.md)|Связывает указанный столбец набора строк.|
|[db_command](../windows/db-command.md)|Создает команду OLE DB.|
|[db_param](../windows/db-param.md)|Связывает указанный член переменной с входным или выходным параметром и разделяет переменной.|
|[db_source](../windows/db-source.md)|Создает подключение к источнику данных.|
|[db_table](../windows/db-table.md)|Открывает таблицу OLE DB.|
|[defaultbind](../windows/defaultbind.md)|Указывает единственное свойство, представляющим объект наилучшим образом.|
|[defaultcollelem](../windows/defaultcollelem.md)|Используется для оптимизации кода Visual Basic.|
|[displaybind](../windows/displaybind.md)|Указывает свойство, которое должно отображаться пользователю как связываемая.|
|[helpcontext](../windows/helpcontext.md)|Указывает идентификатор контекста, который позволяет пользователю просматривать сведения об этом элементе в **помочь** файл.|
|[helpfile](../windows/helpfile.md)|Задает имя **помочь** файл для библиотеки типов.|
|[helpstring](../windows/helpstring.md)|Определяет строку символов, используемую для описания элемента, к которому оно применяется.|
|[helpstringcontext](../windows/helpstringcontext.md)|Указывает идентификатор раздела справки в файл с расширением .hlp или .chm.|
|[helpstringdll](../windows/helpstringdll.md)|Указывает имя библиотеки DLL для выполнения уточняющего запроса строки документа (локализации).|
|[hidden](../windows/hidden.md)|Указывает, что элемент существует, но не должен отображаться в пользовательском браузере.|
|[id](../windows/id.md)|Указывает идентификатор DISPID для функцию-член (свойство или метод, в интерфейс или диспетчерский интерфейс).|
|[immediatebind](../windows/immediatebind.md)|Указывает, что базы данных будет немедленно оповещаться обо всех изменений свойства объекта привязки данных.|
|[in](../windows/in-cpp.md)|Указывает, что параметр передается из вызывающей процедуры вызываемой процедуры.|
|[локальный](../windows/local-cpp.md)|Позволяет использовать в качестве генератор заголовка при использовании в заголовке интерфейс компилятора MIDL. При использовании в отдельной функции, обозначает локальной процедуры, для которого создаются без заглушек.|
|[nonbrowsable](../windows/nonbrowsable.md)|Указывает, что член интерфейса не должен отображаться в обозревателе свойств.|
|[propget](../windows/propget.md)|Указывает функции метода доступа свойства.|
|[propput](../windows/propput.md)|Задает функцию настройки свойства.|
|[propputref](../windows/propputref.md)|Задает функцию настройки свойства, которая использует ссылку вместо значения.|
|[ptr](../windows/ptr.md)|Определяет указатель как полный указатель.|
|[Диапазон](../windows/range-cpp.md)|Указывает диапазон допустимых значений для полей, значения которых устанавливаются во время выполнения и аргументы.|
|[requestedit](../windows/requestedit.md)|Указывает, что свойство поддерживает `OnRequestEdit` уведомлений.|
|[restricted](../windows/restricted.md)|Указывает, что член модуля, интерфейс или диспетчерский интерфейс не может вызываться произвольным образом.|
|[satype](../windows/satype.md)|Указывает тип данных `SAFEARRAY` структуры.|
|[source](../windows/source-cpp.md)|Задает интерфейсы элемента управления источника для точек подключения для класса. Для свойства или метода `source` атрибут указывает, что член возвращает объект или переменная типа VARIANT, являющейся источником событий.|
|[synchronize](../windows/synchronize.md)|Синхронизирует доступ к целевому методу.|
|[vararg](../windows/vararg.md)|Указывает, что функция принимает переменное число аргументов.|

## <a name="see-also"></a>См. также

[Список атрибутов по использованию](../windows/attributes-by-usage.md)