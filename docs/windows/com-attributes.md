---
title: Атрибуты COM | Документы Microsoft
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
ms.openlocfilehash: 9d37ba5c690b61840ad261e6ab966d0cc74c07c1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33861390"
---
# <a name="com-attributes"></a>Атрибуты COM
Атрибуты COM внедрить код для поддержки различных областей разработку COM и .NET Framework типичных языка среды выполнения. Эти области в диапазоне от реализации пользовательского интерфейса, а также поддержку существующие интерфейсы для поддержки стандартных свойств, методов и событий. Кроме того можно получить поддержку для составных и реализации элемента управления ActiveX.  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|[aggregatable](../windows/aggregatable.md)|Указывает, что элемент управления может быть статистически вычислен другого элемента управления.|  
|[aggregates](../windows/aggregates.md)|Указывает, что элемент управления использует статистическую функцию для целевого класса.|  
|[coclass](../windows/coclass.md)|Создает объект COM, который можно реализовать COM-интерфейса.|  
|[COM_INTERFACE_ENTRY](../windows/com-interface-entry-cpp.md)|Добавляет запись интерфейс COM карты.|  
|[implements_category](../windows/implements-category.md)|Определяет категории реализовано компонента для класса.|  
|[progid](../windows/progid.md)|Определяет идентификатор ProgID для элемента управления.|  
|[rdx](../windows/rdx.md)|Создает или изменяет раздел реестра.|  
|[registration_script](../windows/registration-script.md)|Выполняет скрипт указанной регистрации.|  
|[requires_category](../windows/requires-category.md)|Определяет категории необходимый компонент для класса.|  
|[support_error_info](../windows/support-error-info.md)|Поддерживает отчеты об ошибках для целевого объекта.|  
|[synchronize](../windows/synchronize.md)|Синхронизирует доступ к методу.|  
|[Работа с потоками](../windows/threading-cpp.md)|Указывает, что потоковая модель для COM-объекта.|  
|[vi_progid](../windows/vi-progid.md)|Определяет независимый от версии идентификатор ProgID элемента управления.|  
  
## <a name="see-also"></a>См. также  
 [Список атрибутов по группам](../windows/attributes-by-group.md)