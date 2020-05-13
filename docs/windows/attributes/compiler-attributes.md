---
title: Атрибуты компилятора (C++ com)
ms.date: 10/02/2018
helpviewer_keywords:
- cl.exe compiler, attributes
- attributes [C++/CLI], compiler
ms.assetid: 53cd9bee-1521-48ec-b171-80feac2096cc
ms.openlocfilehash: f8eb15645049085acc047e41d0a4ea769d359871
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80168283"
---
# <a name="compiler-attributes"></a>Атрибуты компилятора

Атрибуты компилятора предоставляют различные функциональные возможности.

|attribute|Description|
|---------------|-----------------|
|[emitidl](emitidl.md)|Определяет, будут ли обрабатываться все последующие атрибуты IDL и помещены в созданный IDL-файл.|
|[event_receiver](event-receiver.md)|Создает приемник событий.|
|[event_source](event-source.md)|Создает источник событий.|
|[export](export.md)|Приводит к размещению структуры данных в IDL-файле.|
|[implements](implements-cpp.md)|Указывает интерфейсы диспетчеризации, которые должны быть членами coclass-класса IDL.|
|[importidl](importidl.md)|Вставляет указанный IDL-файл в созданный IDL-файл.|
|[importlib](importlib.md)|Делает типы, которые уже были скомпилированы в другую библиотеку типов, доступными для создаваемой библиотеки типов.|
|[includelib](includelib-cpp.md)|Вызывает включение IDL-или h-файла в созданный IDL-файл.|
|[library_block](library-block.md)|Помещает конструкцию внутрь блока библиотеки IDL-файла.|
|[no_injected_text](no-injected-text.md)|Не позволяет компилятору внедрять код в результате использования атрибута.|
|[satype](satype.md)|Указывает тип данных `SAFEARRAY`.|
|[version](version-cpp.md)|Определяет определенную версию для нескольких версий интерфейса или класса.|

## <a name="see-also"></a>См. также раздел

[Список атрибутов по группам](attributes-by-group.md)
