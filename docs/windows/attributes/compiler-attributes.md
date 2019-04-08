---
title: Атрибуты компилятора (C++ COM)
ms.date: 10/02/2018
helpviewer_keywords:
- cl.exe compiler, attributes
- attributes [C++/CLI], compiler
ms.assetid: 53cd9bee-1521-48ec-b171-80feac2096cc
ms.openlocfilehash: ea4d3119a640c0642664210384c297e011104411
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59030823"
---
# <a name="compiler-attributes"></a>Атрибуты компилятора

Атрибуты компилятора предоставляют широкий набор функций.

|Атрибут|Описание|
|---------------|-----------------|
|[emitidl](emitidl.md)|Определяет, будет ли обработано и помещаются в созданного IDL-файла все последующие атрибуты IDL.|
|[event_receiver](event-receiver.md)|Создает приемник событий.|
|[event_source](event-source.md)|Создает источник событий.|
|[экспорт](export.md)|В результате структуру данных, должно быть помещено в IDL-файла.|
|[реализует](implements-cpp.md)|Указывает диспетчерские интерфейсы, которые нужно принудительно в качестве членов компонентного класса IDL.|
|[importidl](importidl.md)|Вставляет указанный IDL-файла в созданного IDL-файла.|
|[importlib](importlib.md)|Делает типы, которые уже были скомпилированы в другую библиотеку типов, доступными для создаваемой библиотеки типов.|
|[includelib](includelib-cpp.md)|В результате файл IDL или .h, должны быть включены в созданного IDL-файла.|
|[library_block](library-block.md)|Помещает конструкцию внутри блока библиотеки в IDL-файл.|
|[no_injected_text](no-injected-text.md)|Запрещает компилятору вставку кода в результате использования атрибута.|
|[satype](satype.md)|Указывает тип данных `SAFEARRAY`.|
|[version](version-cpp.md)|Идентифицирует конкретную версию несколькими версиями интерфейса или класса.|

## <a name="see-also"></a>См. также

[Список атрибутов по группам](attributes-by-group.md)