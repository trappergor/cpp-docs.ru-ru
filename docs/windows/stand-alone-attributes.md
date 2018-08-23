---
title: Изолированные атрибуты | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- standalone attributes
- attributes [C++], standalone
ms.assetid: 0d72e84e-236c-43b3-ac9a-d9b91fcd6794
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6562a1de8baa9a5805f044233b97bf8dd8840638
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42613762"
---
# <a name="stand-alone-attributes"></a>Изолированные атрибуты
Изолированный атрибут не работают с ключевым словом языка C++, но больше похожи на строки кода. Автономный атрибут инструкций требуется точку с запятой в конце строки.
  
|Атрибут|Описание:|
|---------------|-----------------|
|[cpp_quote](../windows/cpp-quote.md)|Выдает заданную строку, без знаков кавычек в создаваемого файла заголовка.|
|[Custom](../windows/custom-cpp.md)|Позволяет определять собственный атрибут.|
|[db_command](../windows/db-command.md)|Создает команду OLE DB.|
|[emitidl](../windows/emitidl.md)|Определяет, будет ли обработано и помещаются в созданного IDL-файла все последующие атрибуты IDL.|
|[idl_module](../windows/idl-module.md)|Указывает точку входа в библиотеку DLL.|
|[idl_quote](../windows/idl-quote.md)|Позволяет использовать конструкции IDL, которые не поддерживаются в текущей версии Visual C++ и их передачи через созданного IDL-файла.|
|[import](../windows/import.md)|Указывает другой файл .idl, .odl или .h, содержащая определения, как нужно ссылаться из вашей основной IDL-файла.|
|[importidl](../windows/importidl.md)|Вставляет указанный IDL-файла в созданного IDL-файла|
|[importlib](../windows/importlib.md)|Делает типы, которые уже были скомпилированы в другую библиотеку типов, доступными для создаваемой библиотеки типов.|
|[include](../windows/include-cpp.md)|Указывает один или несколько файлов заголовка для включения в созданного IDL-файла.|
|[includelib](../windows/includelib-cpp.md)|В результате файл IDL или .h, должны быть включены в созданного IDL-файла.|
|[library_block](../windows/library-block.md)|Помещает конструкцию внутри блока библиотеки в IDL-файл.|
|[модуль](../windows/module-cpp.md)|Определяет блок библиотеки в IDL-файле.|
|[no_injected_text](../windows/no-injected-text.md)|Запрещает компилятору вставку кода в результате использования атрибута.|
|[pragma](../windows/pragma.md)|Выдает заданную строку, без знаков кавычек в созданного IDL-файла.|
  
## <a name="see-also"></a>См. также
 [Список атрибутов по использованию](../windows/attributes-by-usage.md)