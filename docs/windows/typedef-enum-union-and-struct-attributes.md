---
title: TypeDef, Enum, Union и Struct атрибуты | Документация Майкрософт
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
ms.openlocfilehash: 2e4e8ad94e96c6bfc45102f1c970476c484d756f
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39649127"
---
# <a name="typedef-enum-union-and-struct-attributes"></a>Атрибуты Typedef, Enum, Union и Struct
Следующие атрибуты применяются к [typedef](http://msdn.microsoft.com/cc96cf26-ba93-4179-951e-695d1f5fdcf1), [структуры](../cpp/struct-cpp.md), и [перечисления](../cpp/enumerations-cpp.md) ключевые слова C++.  
  
### <a name="typedef"></a>typedef  
  
|Атрибут|Описание:|  
|---------------|-----------------|  
|[case](../windows/case-cpp.md)|Используется с [switch_type](../windows/switch-type.md) атрибут в **объединение**.|  
|[Custom](../windows/custom-cpp.md)|Позволяет определять собственный атрибут.|  
|[export](../windows/export.md)|В результате структуру данных, должно быть помещено в IDL-файла.|  
|[first_is](../windows/first-is.md)|Указывает индекс первого элемента массива для передачи.|  
|[helpcontext](../windows/helpcontext.md)|Указывает идентификатор контекста, который позволяет пользователю просматривать сведения об этом элементе в файле справки.|  
|[helpfile](../windows/helpfile.md)|Задает имя файла справки для библиотеки типов.|  
|[helpstring](../windows/helpstring.md)|Определяет строку символов, используемую для описания элемента, к которому оно применяется.|  
|[library_block](../windows/library-block.md)|Помещает конструкцию внутри блока библиотеки в IDL-файл.|  
|[ptr](../windows/ptr.md)|Определяет указатель как полный указатель.|  
|[public](../windows/public-cpp-attributes.md)|Гарантирует, что typedef перейдет в библиотеке типов, даже если нет ссылок из в IDL-файла.|  
|[ref](../windows/ref-cpp.md)|Определяет указатель ссылки.|  
|[switch_is](../windows/switch-is.md)|Указывает выражение или идентификатор, действующий как объединения дискриминантный, который выбирает член объединения.|  
|[switch_type](../windows/switch-type.md)|Определяет тип переменной, которая используется в качестве объединения дискриминантный.|  
|[unique](../windows/unique-cpp.md)|Указывает уникальный указатель.|  
|[wire_marshal](../windows/wire-marshal.md)|Указывает тип данных, который будет использоваться для передачи данных вместо типа данных приложения.|  
  
### <a name="enum"></a>перечисление  
  
|Атрибут|Описание:|  
|---------------|-----------------|  
|[Custom](../windows/custom-cpp.md)|Позволяет определять собственный атрибут.|  
|[export](../windows/export.md)|В результате структуру данных, должно быть помещено в IDL-файла.|  
|[uuid](../windows/uuid-cpp-attributes.md)|Указывает уникальный идентификатор для класса или интерфейса.|  
|[v1_enum](../windows/v1-enum.md)|Указывает, что заданного перечислимого типа, передаваться в объект 32-разрядной, а не по умолчанию 16-разрядное.|  
  
### <a name="union"></a>union  
  
|Атрибут|Описание:|  
|---------------|-----------------|  
|[Custom](../windows/custom-cpp.md)|Позволяет определять собственный атрибут.|  
|[export](../windows/export.md)|В результате структуру данных, должно быть помещено в IDL-файла.|  
|[first_is](../windows/first-is.md)|Указывает индекс первого элемента массива для передачи.|  
|[last_is](../windows/last-is.md)|Указывает индекс последнего элемента массива для передачи.|  
|[length_is](../windows/length-is.md)|Указывает количество элементов массива для передачи.|  
|[max_is](../windows/max-is.md)|Определяет максимальное значение для индекса допустимым массивом.|  
|[size_is](../windows/size-is.md)|Указывает объем памяти, выделенной для размера указатели, размер указателей на указатели по размеру и одно - или многомерные массивы.|  
|[unique](../windows/unique-cpp.md)|Указывает уникальный указатель.|  
|[uuid](../windows/uuid-cpp-attributes.md)|Указывает уникальный идентификатор для класса или интерфейса.|  
  
### <a name="nonencapsulated-union"></a>Nonencapsulated union  
  
|Атрибут|Описание:|  
|---------------|-----------------|  
|[ms_union](../windows/ms-union.md)|Управляет выравниванием представление данных сети nonencapsulated объединений.|  
|[no_injected_text](../windows/no-injected-text.md)|Запрещает компилятору вставку кода в результате использования атрибута.|  
  
### <a name="struct"></a>структура  
  
|Атрибут|Описание:|  
|---------------|-----------------|  
|[aggregatable](../windows/aggregatable.md)|Указывает, что класс поддерживает агрегирование.|  
|[aggregates](../windows/aggregates.md)|Указывает, что элемент управления использует статистическую функцию целевого класса.|  
|[appobject](../windows/appobject.md)|Идентифицирует сокласс как объект приложения, который связан с приложением полный .exe и указывает, что функциях и свойствах компонентного класса доступны глобально в этой библиотеки типов.|  
|[coclass](../windows/coclass.md)|Создает элемент управления ActiveX.|  
|[COM_INTERFACE_ENTRY](../windows/com-interface-entry-cpp.md)|Добавляет запись интерфейс COM карты.|  
|[control](../windows/control.md)|Указывает, что определяемый пользователем тип элемента управления.|  
|[Custom](../windows/custom-cpp.md)|Позволяет определять собственный атрибут.|  
|[db_column](../windows/db-column.md)|Связывает указанный столбец набора строк.|  
|[db_command](../windows/db-command.md)|Создает команду OLE DB.|  
|[db_param](../windows/db-param.md)|Связывает указанный член переменной с входным или выходным параметром и разделяет переменной.|  
|[db_source](../windows/db-source.md)|Создает подключение к источнику данных.|  
|[db_table](../windows/db-table.md)|Открывает таблицу OLE DB.|  
|[default](../windows/default-cpp.md)|Указывает, что настраиваемый или disp-интерфейс, определенный в коклассе, представляет интерфейс программирования по умолчанию.|  
|[defaultvtable](../windows/defaultvtable.md)|Определяет интерфейс как интерфейс vtable по умолчанию для элемента управления.|  
|[event_receiver](../windows/event-receiver.md)|Создает приемник событий.|  
|[event_source](../windows/event-source.md)|Создает источник событий.|  
|[export](../windows/export.md)|В результате структуру данных, должно быть помещено в IDL-файла.|  
|[first_is](../windows/first-is.md)|Указывает индекс первого элемента массива для передачи.|  
|[hidden](../windows/hidden.md)|Указывает, что элемент существует, но не должен отображаться в пользовательском браузере.|  
|[implements_category](../windows/implements-category.md)|Указывает категории реализованного компонента для класса.|  
|[last_is](../windows/last-is.md)|Указывает индекс последнего элемента массива для передачи.|  
|[length_is](../windows/length-is.md)|Указывает количество элементов массива для передачи.|  
|[max_is](../windows/max-is.md)|Определяет максимальное значение для индекса допустимым массивом.|  
|[requires_category](../windows/requires-category.md)|Указывает необходимый компонент категории целевого класса.|  
|[size_is](../windows/size-is.md)|Указывает объем памяти, выделенной для размера указатели, размер указателей на указатели по размеру и одно - или многомерные массивы.|  
|[source](../windows/source-cpp.md)|В классе, задает интерфейсы COM-объекта источника для точек подключения. На свойства или метода указывает, что член возвращает объект или переменная типа VARIANT, являющейся источником событий.|  
|[Работа с потоками](../windows/threading-cpp.md)|Указывает потоковую модель для COM-объекта.|  
|[unique](../windows/unique-cpp.md)|Указывает уникальный указатель.|  
|[uuid](../windows/uuid-cpp-attributes.md)|Указывает уникальный идентификатор для класса или интерфейса.|  
|[version](../windows/version-cpp.md)|Идентифицирует конкретную версию несколькими версиями класса.|  
|[vi_progid](../windows/vi-progid.md)|Указывает форму независящим от версии идентификатор ProgID.|  
  
## <a name="see-also"></a>См. также  
 [Список атрибутов по использованию](../windows/attributes-by-usage.md)