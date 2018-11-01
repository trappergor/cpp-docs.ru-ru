---
title: Атрибуты COM
ms.date: 10/03/2018
helpviewer_keywords:
- attributes [C++/CLI], reference topics
- attributes [COM]
- COM, attributes
ms.assetid: 52a5dd70-e8be-4bba-afd6-daf90fe689a0
ms.openlocfilehash: fa7e279f6b7c9c0932d404c336bcfd89bfd553a3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50644097"
---
# <a name="com-attributes"></a>Атрибуты COM

Атрибуты COM вставки кода для поддержки множество различных областей разработки COM и .NET Framework среды выполнения разработки языка. Эти области варьируются от реализации пользовательского интерфейса, а также поддержку существующих интерфейсов для поддержки стандартных свойств, методов и событий. Кроме того можно получить поддержку для составных и реализации элемента управления ActiveX.

|Атрибут|Описание|
|---------------|-----------------|
|[aggregatable](aggregatable.md)|Указывает, что элемент управления может быть статистически вычислен другим элементом управления.|
|[aggregates](aggregates.md)|Указывает, что элемент управления использует статистическую функцию целевого класса.|
|[кокласс](coclass.md)|Создает объект COM, который можно реализовать COM-интерфейса.|
|[com_interface_entry](com-interface-entry-cpp.md)|Добавляет запись интерфейс COM карты.|
|[implements_category](implements-category.md)|Указывает категории реализованного компонента для класса.|
|[progid](progid.md)|Определяет идентификатор ProgID для элемента управления.|
|[rdx](rdx.md)|Создает или изменяет раздел реестра.|
|[registration_script](registration-script.md)|Выполняет скрипт указанную регистрацию.|
|[requires_category](requires-category.md)|Указывает категории необходимый компонент для класса.|
|[support_error_info](support-error-info.md)|Поддерживает об ошибках для целевого объекта.|
|[synchronize](synchronize.md)|Синхронизирует доступ к методу.|
|[threading](threading-cpp.md)|Указывает потоковую модель для COM-объекта.|
|[vi_progid](vi-progid.md)|Определяет независимый от версии идентификатор ProgID для элемента управления.|

## <a name="see-also"></a>См. также

[Список атрибутов по группам](attributes-by-group.md)