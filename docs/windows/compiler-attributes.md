---
title: Атрибуты компилятора | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, attributes
- attributes [C++/CLI], compiler
ms.assetid: 53cd9bee-1521-48ec-b171-80feac2096cc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1c1ce698992f1f34434a476be83da6f4697f619c
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44316540"
---
# <a name="compiler-attributes"></a>Атрибуты компилятора

Атрибуты компилятора предоставляют широкий набор функций.

|Атрибут|Описание|
|---------------|-----------------|
|[emitidl](../windows/emitidl.md)|Определяет, будет ли обработано и помещаются в созданного IDL-файла все последующие атрибуты IDL.|
|[event_receiver](../windows/event-receiver.md)|Создает приемник событий.|
|[event_source](../windows/event-source.md)|Создает источник событий.|
|[export](../windows/export.md)|В результате структуру данных, должно быть помещено в IDL-файла.|
|[Реализует](../windows/implements-cpp.md)|Указывает диспетчерские интерфейсы, которые нужно принудительно в качестве членов компонентного класса IDL.|
|[importidl](../windows/importidl.md)|Вставляет указанный IDL-файла в созданного IDL-файла.|
|[importlib](../windows/importlib.md)|Делает типы, которые уже были скомпилированы в другую библиотеку типов, доступными для создаваемой библиотеки типов.|
|[includelib](../windows/includelib-cpp.md)|В результате файл IDL или .h, должны быть включены в созданного IDL-файла.|
|[library_block](../windows/library-block.md)|Помещает конструкцию внутри блока библиотеки в IDL-файл.|
|[no_injected_text](../windows/no-injected-text.md)|Запрещает компилятору вставку кода в результате использования атрибута.|
|[satype](../windows/satype.md)|Указывает тип данных `SAFEARRAY`.|
|[version](../windows/version-cpp.md)|Идентифицирует конкретную версию несколькими версиями интерфейса или класса.|

## <a name="see-also"></a>См. также

[Список атрибутов по группам](../windows/attributes-by-group.md)