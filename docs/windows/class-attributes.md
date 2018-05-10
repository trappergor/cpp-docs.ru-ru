---
title: Класс атрибутов | Документы Microsoft
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
ms.openlocfilehash: 8a932fdb1ef1d9e2af2acace901feaa95b6216d1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="class-attributes"></a>Атрибуты классов
Следующие атрибуты, относящиеся к [класса](../cpp/class-cpp.md) C++ ключевое слово.  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|[aggregatable](../windows/aggregatable.md)|Указывает, что класс поддерживает агрегирование.|  
|[aggregates](../windows/aggregates.md)|Указывает, что элемент управления использует статистическую функцию для целевого класса.|  
|[appobject](../windows/appobject.md)|Идентифицирует компонентного класса, как объект приложения, который связан с приложением полный .exe и указывает, что функциях и свойствах компонентного класса доступны глобально в этой библиотеке типов.|  
|[case](../windows/case-cpp.md)|При использовании [switch_type](../windows/switch-type.md) атрибута в объединении.|  
|[coclass](../windows/coclass.md)|Создает элемент управления ActiveX.|  
|[COM_INTERFACE_ENTRY](../windows/com-interface-entry-cpp.md)|Добавляет запись интерфейс COM карты.|  
|[control](../windows/control.md)|Указывает, что определяемый пользователем тип элемента управления.|  
|[Настройка](../windows/custom-cpp.md)|Позволяет определять собственный атрибут.|  
|[db_command](../windows/db-command.md)|Создает команду OLE DB.|  
|[db_param](../windows/db-param.md)|Связывает указанный член переменной с входным или выходным параметром и разделяет переменной.|  
|[db_source](../windows/db-source.md)|Создает подключение к источнику данных.|  
|[db_table](../windows/db-table.md)|Открывает таблицу OLE DB.|  
|[default](../windows/default-cpp.md)|Указывает, что настраиваемый или disp-интерфейс, определенный в коклассе, представляет интерфейс программирования по умолчанию.|  
|[defaultvtable](../windows/defaultvtable.md)|Определяет интерфейс как интерфейс vtable по умолчанию для элемента управления.|  
|[event_receiver](../windows/event-receiver.md)|Создает приемник событий.|  
|[event_source](../windows/event-source.md)|Создает источник событий.|  
|[helpcontext](../windows/helpcontext.md)|Указывает идентификатор контекста, который позволяет пользователю просматривать сведения об этом элементе в файле справки.|  
|[helpfile](../windows/helpfile.md)|Задает имя файла справки для библиотеки типов.|  
|[helpstringcontext](../windows/helpstringcontext.md)|Указывает идентификатор раздела справки в .hlp или CHM-файле.|  
|[helpstring](../windows/helpstring.md)|Определяет строку символов, используемый для описания элемента, к которому он применяется.|  
|[hidden](../windows/hidden.md)|Указывает, что элемент существует, но не должен отображаться в пользовательском браузере.|  
|[Реализует](../windows/implements-cpp.md)|Задает интерфейсы диспетчеризации, преобразуются в качестве членов IDL coclass.|  
|[implements_category](../windows/implements-category.md)|Определяет категории реализовано компонента для класса.|  
|[Модуль](../windows/module-cpp.md)|Определяет блок библиотеки в IDL-файле.|  
|[noncreatable](../windows/noncreatable.md)|Определяет объект, который не может быть создан сам по себе.|  
|[progid](../windows/progid.md)|Определяет идентификатор ProgID для элемента управления.|  
|[registration_script](../windows/registration-script.md)|Выполняет скрипт указанной регистрации.|  
|[requestedit](../windows/requestedit.md)|Указывает, что свойство поддерживает **OnRequestEdit** уведомления.|  
|[Источник](../windows/source-cpp.md)|Определяет класс исходных интерфейсов элемента управления для точки подключения. Для свойства или метода **источника** атрибут указывает, что член возвращает объект или ВАРИАНТ, который является источником событий.|  
|[support_error_info](../windows/support-error-info.md)|Поддерживает отчеты об ошибках для целевого объекта.|  
|[Работа с потоками](../windows/threading-cpp.md)|Указывает, что потоковая модель для элемента управления.|  
|[uuid](../windows/uuid-cpp-attributes.md)|Указывает уникальный идентификатор для класса или интерфейса.|  
|[version](../windows/version-cpp.md)|Определяет конкретную версию несколькими версиями класса.|  
|[vi_progid](../windows/vi-progid.md)|Указывает форму независимый от версии идентификатор ProgID.|  
  
## <a name="see-also"></a>См. также  
 [Список атрибутов по использованию](../windows/attributes-by-usage.md)