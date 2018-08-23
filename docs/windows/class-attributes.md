---
title: Класс атрибутов | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++], class attributes
- class attributes
ms.assetid: fad04ea1-d8ff-46d4-bb42-2b4500a6ab60
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5b0057fa97805c093df7cac126e87f9af0a98a73
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42611897"
---
# <a name="class-attributes"></a>Атрибуты классов

Следующие атрибуты применяются к [класс](../cpp/class-cpp.md) ключевым словом языка C++.

|Атрибут|Описание:|
|---------------|-----------------|
|[aggregatable](../windows/aggregatable.md)|Указывает, что класс поддерживает агрегирование.|
|[aggregates](../windows/aggregates.md)|Указывает, что элемент управления использует статистическую функцию целевого класса.|
|[appobject](../windows/appobject.md)|Идентифицирует сокласс как объект приложения, который связан с приложением полный .exe и указывает, что функциях и свойствах компонентного класса доступны глобально в этой библиотеки типов.|
|[case](../windows/case-cpp.md)|Используется с [switch_type](../windows/switch-type.md) атрибут в объединении.|
|[coclass](../windows/coclass.md)|Создает элемент управления ActiveX.|
|[COM_INTERFACE_ENTRY](../windows/com-interface-entry-cpp.md)|Добавляет запись интерфейс COM карты.|
|[control](../windows/control.md)|Указывает, что определяемый пользователем тип элемента управления.|
|[Custom](../windows/custom-cpp.md)|Позволяет определять собственный атрибут.|
|[db_command](../windows/db-command.md)|Создает команду OLE DB.|
|[db_param](../windows/db-param.md)|Связывает указанный член переменной с входным или выходным параметром и разделяет переменной.|
|[db_source](../windows/db-source.md)|Создает подключение к источнику данных.|
|[db_table](../windows/db-table.md)|Открывает таблицу OLE DB.|
|[default](../windows/default-cpp.md)|Указывает, что настраиваемый или disp-интерфейс, определенный в коклассе, представляет интерфейс программирования по умолчанию.|
|[defaultvtable](../windows/defaultvtable.md)|Определяет интерфейс как интерфейс vtable по умолчанию для элемента управления.|
|[event_receiver](../windows/event-receiver.md)|Создает приемник событий.|
|[event_source](../windows/event-source.md)|Создает источник событий.|
|[helpcontext](../windows/helpcontext.md)|Указывает идентификатор контекста, который позволяет пользователю просматривать сведения об этом элементе в **помочь** файл.|
|[helpfile](../windows/helpfile.md)|Задает имя файла справки для библиотеки типов.|
|[helpstringcontext](../windows/helpstringcontext.md)|Указывает идентификатор раздела справки в файл с расширением .hlp или .chm.|
|[helpstring](../windows/helpstring.md)|Определяет строку символов, используемую для описания элемента, к которому оно применяется.|
|[hidden](../windows/hidden.md)|Указывает, что элемент существует, но не должен отображаться в пользовательском браузере.|
|[Реализует](../windows/implements-cpp.md)|Указывает диспетчерские интерфейсы, которые нужно принудительно в качестве членов компонентного класса IDL.|
|[implements_category](../windows/implements-category.md)|Указывает категории реализованного компонента для класса.|
|[модуль](../windows/module-cpp.md)|Определяет блок библиотеки в IDL-файле.|
|[noncreatable](../windows/noncreatable.md)|Определяет объект, который не может быть создан сама по себе.|
|[progid](../windows/progid.md)|Определяет идентификатор ProgID для элемента управления.|
|[registration_script](../windows/registration-script.md)|Выполняет скрипт указанную регистрацию.|
|[requestedit](../windows/requestedit.md)|Указывает, что свойство поддерживает `OnRequestEdit` уведомлений.|
|[source](../windows/source-cpp.md)|Задает интерфейсы элемента управления источника для точек подключения для класса. Для свойства или метода `source` атрибут указывает, что член возвращает объект или `VARIANT` то есть источником событий.|
|[support_error_info](../windows/support-error-info.md)|Поддерживает об ошибках для целевого объекта.|
|[Работа с потоками](../windows/threading-cpp.md)|Указывает потоковую модель для элемента управления.|
|[uuid](../windows/uuid-cpp-attributes.md)|Указывает уникальный идентификатор для класса или интерфейса.|
|[version](../windows/version-cpp.md)|Идентифицирует конкретную версию несколькими версиями класса.|
|[vi_progid](../windows/vi-progid.md)|Указывает форму независящим от версии идентификатор ProgID.|

## <a name="see-also"></a>См. также

[Список атрибутов по использованию](../windows/attributes-by-usage.md)