---
title: Атрибуты COM | Документация Майкрософт
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++/CLI], reference topics
- attributes [COM]
- COM, attributes
ms.assetid: 52a5dd70-e8be-4bba-afd6-daf90fe689a0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 83d518aded30215684970e58d2868625fb8cd0e5
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48792449"
---
# <a name="com-attributes"></a>Атрибуты COM

Атрибуты COM вставки кода для поддержки множество различных областей разработки COM и .NET Framework среды выполнения разработки языка. Эти области варьируются от реализации пользовательского интерфейса, а также поддержку существующих интерфейсов для поддержки стандартных свойств, методов и событий. Кроме того можно получить поддержку для составных и реализации элемента управления ActiveX.
  
|Атрибут|Описание|
|---------------|-----------------|
|[aggregatable](aggregatable.md)|Указывает, что элемент управления может быть статистически вычислен другим элементом управления.|
|[aggregates](aggregates.md)|Указывает, что элемент управления использует статистическую функцию целевого класса.|
|[coclass](coclass.md)|Создает объект COM, который можно реализовать COM-интерфейса.|
|[COM_INTERFACE_ENTRY](com-interface-entry-cpp.md)|Добавляет запись интерфейс COM карты.|
|[implements_category](implements-category.md)|Указывает категории реализованного компонента для класса.|
|[progid](progid.md)|Определяет идентификатор ProgID для элемента управления.|
|[rdx](rdx.md)|Создает или изменяет раздел реестра.|
|[registration_script](registration-script.md)|Выполняет скрипт указанную регистрацию.|
|[requires_category](requires-category.md)|Указывает категории необходимый компонент для класса.|
|[support_error_info](support-error-info.md)|Поддерживает об ошибках для целевого объекта.|
|[synchronize](synchronize.md)|Синхронизирует доступ к методу.|
|[Работа с потоками](threading-cpp.md)|Указывает потоковую модель для COM-объекта.|
|[vi_progid](vi-progid.md)|Определяет независимый от версии идентификатор ProgID для элемента управления.|
  
## <a name="see-also"></a>См. также

[Список атрибутов по группам](attributes-by-group.md)