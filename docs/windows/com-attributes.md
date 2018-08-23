---
title: Атрибуты COM | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++], reference topics
- attributes [COM]
- COM, attributes
ms.assetid: 52a5dd70-e8be-4bba-afd6-daf90fe689a0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 857e032f02102a79747b79140207d07905f5b3d2
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42591595"
---
# <a name="com-attributes"></a>Атрибуты COM
Атрибуты COM вставки кода для поддержки множество различных областей разработки COM и .NET Framework среды выполнения разработки языка. Эти области варьируются от реализации пользовательского интерфейса, а также поддержку существующих интерфейсов для поддержки стандартных свойств, методов и событий. Кроме того можно получить поддержку для составных и реализации элемента управления ActiveX.
  
|Атрибут|Описание:|
|---------------|-----------------|
|[aggregatable](../windows/aggregatable.md)|Указывает, что элемент управления может быть статистически вычислен другим элементом управления.|
|[aggregates](../windows/aggregates.md)|Указывает, что элемент управления использует статистическую функцию целевого класса.|
|[coclass](../windows/coclass.md)|Создает объект COM, который можно реализовать COM-интерфейса.|
|[COM_INTERFACE_ENTRY](../windows/com-interface-entry-cpp.md)|Добавляет запись интерфейс COM карты.|
|[implements_category](../windows/implements-category.md)|Указывает категории реализованного компонента для класса.|
|[progid](../windows/progid.md)|Определяет идентификатор ProgID для элемента управления.|
|[rdx](../windows/rdx.md)|Создает или изменяет раздел реестра.|
|[registration_script](../windows/registration-script.md)|Выполняет скрипт указанную регистрацию.|
|[requires_category](../windows/requires-category.md)|Указывает категории необходимый компонент для класса.|
|[support_error_info](../windows/support-error-info.md)|Поддерживает об ошибках для целевого объекта.|
|[synchronize](../windows/synchronize.md)|Синхронизирует доступ к методу.|
|[Работа с потоками](../windows/threading-cpp.md)|Указывает потоковую модель для COM-объекта.|
|[vi_progid](../windows/vi-progid.md)|Определяет независимый от версии идентификатор ProgID для элемента управления.|
  
## <a name="see-also"></a>См. также
 [Список атрибутов по группам](../windows/attributes-by-group.md)