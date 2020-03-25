---
title: Атрибуты COM
ms.date: 10/03/2018
helpviewer_keywords:
- attributes [C++/CLI], reference topics
- attributes [COM]
- COM, attributes
ms.assetid: 52a5dd70-e8be-4bba-afd6-daf90fe689a0
ms.openlocfilehash: 15225d23abb66b8aadd5f82b8429334356bdaa8d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80168321"
---
# <a name="com-attributes"></a>Атрибуты COM

Атрибуты COM вставляют код для поддержки многочисленных областей разработки COM и .NET Framework разработки среды CLR. Эти области изменяются от реализации пользовательского интерфейса и поддержки существующих интерфейсов для поддержки стандартных свойств, методов и событий. Кроме того, поддержку можно найти для реализации составных и элементов управления ActiveX.

|attribute|Description|
|---------------|-----------------|
|[aggregatable](aggregatable.md)|Указывает, что элемент управления может быть агрегирован другим элементом управления.|
|[aggregates](aggregates.md)|Указывает, что элемент управления выполняет статистическую обработку целевого класса.|
|[кокласс](coclass.md)|Создает COM-объект, который может реализовать интерфейс COM.|
|[com_interface_entry](com-interface-entry-cpp.md)|Добавляет запись интерфейса в карту COM.|
|[implements_category](implements-category.md)|Задает категории реализованного компонента для класса.|
|[progid](progid.md)|Определяет ProgID для элемента управления.|
|[rdx](rdx.md)|Создает или изменяет раздел реестра.|
|[registration_script](registration-script.md)|Выполняет указанный скрипт регистрации.|
|[requires_category](requires-category.md)|Указывает обязательные категории компонентов для класса.|
|[support_error_info](support-error-info.md)|Поддерживает отчеты об ошибках для целевого объекта.|
|[synchronize](synchronize.md)|Синхронизирует доступ к методу.|
|[threading](threading-cpp.md)|Указывает потоковую модель для COM-объекта.|
|[vi_progid](vi-progid.md)|Определяет независимый от версии идентификатор ProgID для элемента управления.|

## <a name="see-also"></a>См. также раздел

[Список атрибутов по группам](attributes-by-group.md)
