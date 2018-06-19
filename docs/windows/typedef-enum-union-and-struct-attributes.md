---
title: TypeDef, Enum, Union и Struct атрибуты | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- union attributes
- attributes [C++], reference topics
- struct attributes
- typedef attributes
- enum attributes
ms.assetid: f8a4fe94-dc02-4aed-bc31-3e500d42f4c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c14881afd000dc5fb4223a2ecfa9dcdc67e7b541
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33891835"
---
# <a name="typedef-enum-union-and-struct-attributes"></a>Атрибуты Typedef, Enum, Union и Struct
Следующие атрибуты, относящиеся к [typedef](http://msdn.microsoft.com/en-us/cc96cf26-ba93-4179-951e-695d1f5fdcf1), [структуры](../cpp/struct-cpp.md), и [перечисления](../cpp/enumerations-cpp.md) ключевые слова C++.  
  
### <a name="typedef"></a>typedef  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|[case](../windows/case-cpp.md)|При использовании [switch_type](../windows/switch-type.md) атрибута в **объединение**.|  
|[Настройка](../windows/custom-cpp.md)|Позволяет определять собственный атрибут.|  
|[export](../windows/export.md)|В результате структуру данных помещается в IDL-файл.|  
|[first_is](../windows/first-is.md)|Указывает индекс первого элемента массива для передачи.|  
|[helpcontext](../windows/helpcontext.md)|Указывает идентификатор контекста, который позволяет пользователю просматривать сведения об этом элементе в файле справки.|  
|[helpfile](../windows/helpfile.md)|Задает имя файла справки для библиотеки типов.|  
|[helpstring](../windows/helpstring.md)|Определяет строку символов, используемый для описания элемента, к которому он применяется.|  
|[library_block](../windows/library-block.md)|Помещает конструкцию внутри блока библиотеки IDL-файл.|  
|[ptr](../windows/ptr.md)|Определяет указатель как полный указатель.|  
|[public](../windows/public-cpp-attributes.md)|Гарантирует, что typedef перейдет в библиотеке типов, даже если нет ссылок из в IDL-файл.|  
|[ref](../windows/ref-cpp.md)|Определяет указатель ссылки.|  
|[switch_is](../windows/switch-is.md)|Указывает выражение или идентификатор, выступающего в качестве объединения дискриминантный, который выбирает члена объединения.|  
|[switch_type](../windows/switch-type.md)|Определяет тип переменной, которая используется как дискриминантный объединения.|  
|[unique](../windows/unique-cpp.md)|Указывает уникальный указатель.|  
|[wire_marshal](../windows/wire-marshal.md)|Указывает тип данных, который будет использоваться для передачи данных вместо типа данных приложения.|  
  
### <a name="enum"></a>перечисление  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|[Настройка](../windows/custom-cpp.md)|Позволяет определять собственный атрибут.|  
|[export](../windows/export.md)|В результате структуру данных помещается в IDL-файл.|  
|[uuid](../windows/uuid-cpp-attributes.md)|Указывает уникальный идентификатор для класса или интерфейса.|  
|[v1_enum](../windows/v1-enum.md)|Направляет передачи заданного перечислимого типа как сущность 32 бита, а не 16-разрядное значение по умолчанию.|  
  
### <a name="union"></a>union  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|[Настройка](../windows/custom-cpp.md)|Позволяет определять собственный атрибут.|  
|[export](../windows/export.md)|В результате структуру данных помещается в IDL-файл.|  
|[first_is](../windows/first-is.md)|Указывает индекс первого элемента массива для передачи.|  
|[last_is](../windows/last-is.md)|Определяет индекс последнего элемента массива для передачи.|  
|[length_is](../windows/length-is.md)|Указывает количество элементов массива, для передачи.|  
|[max_is](../windows/max-is.md)|Задает максимальное значение для индекса массива допустимым.|  
|[size_is](../windows/size-is.md)|Указывает объем памяти, выделенной для указателей, по размеру, размер указателей на указатели по размеру и одно - или многомерные массивы.|  
|[unique](../windows/unique-cpp.md)|Указывает уникальный указатель.|  
|[uuid](../windows/uuid-cpp-attributes.md)|Указывает уникальный идентификатор для класса или интерфейса.|  
  
### <a name="nonencapsulated-union"></a>Nonencapsulated объединения  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|[ms_union](../windows/ms-union.md)|Управляет выравниванием представление данных сети nonencapsulated объединений.|  
|[no_injected_text](../windows/no-injected-text.md)|Запрещает компилятору встраивать код в результате использования атрибута.|  
  
### <a name="struct"></a>структура  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|[aggregatable](../windows/aggregatable.md)|Указывает, что класс поддерживает агрегирование.|  
|[aggregates](../windows/aggregates.md)|Указывает, что элемент управления использует статистическую функцию для целевого класса.|  
|[appobject](../windows/appobject.md)|Идентифицирует компонентного класса, как объект приложения, который связан с приложением полный .exe и указывает, что функциях и свойствах компонентного класса доступны глобально в этой библиотеке типов.|  
|[coclass](../windows/coclass.md)|Создает элемент управления ActiveX.|  
|[COM_INTERFACE_ENTRY](../windows/com-interface-entry-cpp.md)|Добавляет запись интерфейс COM карты.|  
|[control](../windows/control.md)|Указывает, что определяемый пользователем тип элемента управления.|  
|[Настройка](../windows/custom-cpp.md)|Позволяет определять собственный атрибут.|  
|[db_column](../windows/db-column.md)|Связывает указанный столбец набора строк.|  
|[db_command](../windows/db-command.md)|Создает команду OLE DB.|  
|[db_param](../windows/db-param.md)|Связывает указанный член переменной с входным или выходным параметром и разделяет переменной.|  
|[db_source](../windows/db-source.md)|Создает подключение к источнику данных.|  
|[db_table](../windows/db-table.md)|Открывает таблицу OLE DB.|  
|[default](../windows/default-cpp.md)|Указывает, что настраиваемый или disp-интерфейс, определенный в коклассе, представляет интерфейс программирования по умолчанию.|  
|[defaultvtable](../windows/defaultvtable.md)|Определяет интерфейс как интерфейс vtable по умолчанию для элемента управления.|  
|[event_receiver](../windows/event-receiver.md)|Создает приемник событий.|  
|[event_source](../windows/event-source.md)|Создает источник событий.|  
|[export](../windows/export.md)|В результате структуру данных помещается в IDL-файл.|  
|[first_is](../windows/first-is.md)|Указывает индекс первого элемента массива для передачи.|  
|[hidden](../windows/hidden.md)|Указывает, что элемент существует, но не должен отображаться в пользовательском браузере.|  
|[implements_category](../windows/implements-category.md)|Определяет категории реализовано компонента для класса.|  
|[last_is](../windows/last-is.md)|Определяет индекс последнего элемента массива для передачи.|  
|[length_is](../windows/length-is.md)|Указывает количество элементов массива, для передачи.|  
|[max_is](../windows/max-is.md)|Задает максимальное значение для индекса массива допустимым.|  
|[requires_category](../windows/requires-category.md)|Задает категории обязательный компонент целевого класса.|  
|[size_is](../windows/size-is.md)|Указывает объем памяти, выделенной для указателей, по размеру, размер указателей на указатели по размеру и одно - или многомерные массивы.|  
|[Источник](../windows/source-cpp.md)|В классе задает исходных интерфейсов COM-объект для точки подключения. Для свойства или метода означает, что член возвращает объект или ВАРИАНТ, который является источником событий.|  
|[Работа с потоками](../windows/threading-cpp.md)|Указывает, что потоковая модель для COM-объекта.|  
|[unique](../windows/unique-cpp.md)|Указывает уникальный указатель.|  
|[uuid](../windows/uuid-cpp-attributes.md)|Указывает уникальный идентификатор для класса или интерфейса.|  
|[version](../windows/version-cpp.md)|Определяет конкретную версию несколькими версиями класса.|  
|[vi_progid](../windows/vi-progid.md)|Указывает форму независимый от версии идентификатор ProgID.|  
  
## <a name="see-also"></a>См. также  
 [Список атрибутов по использованию](../windows/attributes-by-usage.md)