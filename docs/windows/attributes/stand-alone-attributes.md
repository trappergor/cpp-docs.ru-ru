---
title: Изолированные атрибуты (C++ COM)
ms.date: 10/02/2018
helpviewer_keywords:
- standalone attributes
- attributes [C++/CLI], standalone
ms.assetid: 0d72e84e-236c-43b3-ac9a-d9b91fcd6794
ms.openlocfilehash: 1183d2b171a25b3b2d1aef14c19f81be65effc6a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50640832"
---
# <a name="stand-alone-attributes"></a>Изолированные атрибуты

Изолированный атрибут не работают с ключевым словом языка C++, но больше похожи на строки кода. Автономный атрибут инструкций требуется точку с запятой в конце строки.

## <a name="stand-alone-attribute-list"></a>Список атрибутов, изолированный

|Атрибут|Описание|
|---------------|-----------------|
|[cpp_quote](cpp-quote.md)|Выдает заданную строку, без знаков кавычек в создаваемого файла заголовка.|
|[custom](custom-cpp.md)|Позволяет определять собственный атрибут.|
|[db_command](db-command.md)|Создает команду OLE DB.|
|[emitidl](emitidl.md)|Определяет, будет ли обработано и помещаются в созданного IDL-файла все последующие атрибуты IDL.|
|[idl_module](idl-module.md)|Указывает точку входа в библиотеку DLL.|
|[idl_quote](idl-quote.md)|Позволяет использовать конструкции IDL, которые не поддерживаются в текущей версии Visual C++ и их передачи через созданного IDL-файла.|
|[import](import.md)|Указывает другой файл .idl, .odl или .h, содержащая определения, как нужно ссылаться из вашей основной IDL-файла.|
|[importidl](importidl.md)|Вставляет указанный IDL-файла в созданного IDL-файла|
|[importlib](importlib.md)|Делает типы, которые уже были скомпилированы в другую библиотеку типов, доступными для создаваемой библиотеки типов.|
|[include](include-cpp.md)|Указывает один или несколько файлов заголовка для включения в созданного IDL-файла.|
|[includelib](includelib-cpp.md)|В результате файл IDL или .h, должны быть включены в созданного IDL-файла.|
|[library_block](library-block.md)|Помещает конструкцию внутри блока библиотеки в IDL-файл.|
|[module](module-cpp.md)|Определяет блок библиотеки в IDL-файле.|
|[no_injected_text](no-injected-text.md)|Запрещает компилятору вставку кода в результате использования атрибута.|
|[pragma](pragma.md)|Выдает заданную строку, без знаков кавычек в созданного IDL-файла.|

## <a name="see-also"></a>См. также

[Список атрибутов по использованию](attributes-by-usage.md)