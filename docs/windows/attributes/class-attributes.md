---
title: Атрибуты классов (C++ COM)
ms.date: 10/02/2018
helpviewer_keywords:
- attributes [C++/CLI], class attributes
ms.assetid: fad04ea1-d8ff-46d4-bb42-2b4500a6ab60
ms.openlocfilehash: d0913d09c51734f5255271c0d06e639810e0cb58
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62148423"
---
# <a name="class-attributes"></a>Атрибуты классов

Следующие атрибуты применяются к [класс](../../cpp/class-cpp.md) ключевым словом языка C++.

|Атрибут|Описание|
|---------------|-----------------|
|[aggregatable](aggregatable.md)|Указывает, что класс поддерживает агрегирование.|
|[aggregates](aggregates.md)|Указывает, что элемент управления использует статистическую функцию целевого класса.|
|[appobject](appobject.md)|Идентифицирует сокласс как объект приложения, который связан с приложением полный .exe и указывает, что функциях и свойствах компонентного класса доступны глобально в этой библиотеки типов.|
|[case](case-cpp.md)|Используется с [switch_type](switch-type.md) атрибут в объединении.|
|[кокласс](coclass.md)|Создает элемент управления ActiveX.|
|[com_interface_entry](com-interface-entry-cpp.md)|Добавляет запись интерфейс COM карты.|
|[control](control.md)|Указывает, что определяемый пользователем тип элемента управления.|
|[custom](custom-cpp.md)|Позволяет определять собственный атрибут.|
|[db_command](db-command.md)|Создает команду OLE DB.|
|[db_param](db-param.md)|Связывает указанный член переменной с входным или выходным параметром и разделяет переменной.|
|[db_source](db-source.md)|Создает подключение к источнику данных.|
|[db_table](db-table.md)|Открывает таблицу OLE DB.|
|[default](default-cpp.md)|Указывает, что настраиваемый или disp-интерфейс, определенный в коклассе, представляет интерфейс программирования по умолчанию.|
|[defaultvtable](defaultvtable.md)|Определяет интерфейс как интерфейс vtable по умолчанию для элемента управления.|
|[event_receiver](event-receiver.md)|Создает приемник событий.|
|[event_source](event-source.md)|Создает источник событий.|
|[helpcontext](helpcontext.md)|Указывает идентификатор контекста, который позволяет пользователю просматривать сведения об этом элементе в **помочь** файл.|
|[helpfile](helpfile.md)|Задает имя файла справки для библиотеки типов.|
|[helpstringcontext](helpstringcontext.md)|Указывает идентификатор раздела справки в файл с расширением .hlp или .chm.|
|[helpstring](helpstring.md)|Определяет строку символов, используемую для описания элемента, к которому оно применяется.|
|[hidden](hidden.md)|Указывает, что элемент существует, но не должен отображаться в пользовательском браузере.|
|[implements](implements-cpp.md)|Указывает диспетчерские интерфейсы, которые нужно принудительно в качестве членов компонентного класса IDL.|
|[implements_category](implements-category.md)|Указывает категории реализованного компонента для класса.|
|[module](module-cpp.md)|Определяет блок библиотеки в IDL-файле.|
|[noncreatable](noncreatable.md)|Определяет объект, который не может быть создан сама по себе.|
|[progid](progid.md)|Определяет идентификатор ProgID для элемента управления.|
|[registration_script](registration-script.md)|Выполняет скрипт указанную регистрацию.|
|[requestedit](requestedit.md)|Указывает, что свойство поддерживает уведомление `OnRequestEdit`.|
|[source](source-cpp.md)|Задает интерфейсы элемента управления источника для точек подключения для класса. Для свойства или метода `source` атрибут указывает, что член возвращает объект или `VARIANT` то есть источником событий.|
|[support_error_info](support-error-info.md)|Поддерживает об ошибках для целевого объекта.|
|[threading](threading-cpp.md)|Указывает потоковую модель для элемента управления.|
|[uuid](uuid-cpp-attributes.md)|Указывает уникальный идентификатор для класса или интерфейса.|
|[version](version-cpp.md)|Идентифицирует конкретную версию несколькими версиями класса.|
|[vi_progid](vi-progid.md)|Указывает форму независящим от версии идентификатор ProgID.|

## <a name="see-also"></a>См. также

[Список атрибутов по использованию](attributes-by-usage.md)