---
title: Изолированные атрибуты | Документы Microsoft
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
ms.openlocfilehash: 59846b1ca031cc02c85cb6ace23f96e8c5cc9f37
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="stand-alone-attributes"></a>Изолированные атрибуты
Изолированный атрибут не действует в C++ ключевое слово, но больше похожи на строки кода. Инструкции автономный атрибут необходимые точку с запятой в конец строки.  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|[cpp_quote](../windows/cpp-quote.md)|Создает указанную строку без символов кавычек, в создаваемого заголовочного файла.|  
|[Настройка](../windows/custom-cpp.md)|Позволяет определять собственный атрибут.|  
|[db_command](../windows/db-command.md)|Создает команду OLE DB.|  
|[emitidl](../windows/emitidl.md)|Определяет, будут обработаны и помещен в сгенерированный IDL-файл все последующие атрибуты IDL.|  
|[idl_module](../windows/idl-module.md)|Задает точку входа в библиотеку DLL.|  
|[idl_quote](../windows/idl-quote.md)|Позволяет использовать IDL конструкции, которые не поддерживаются в текущей версии Visual C++ и их передачи через созданного IDL-файла.|  
|[import](../windows/import.md)|Указывает другой файл IDL, .odl или .h содержит определения, необходимые для ссылки из вашей главной IDL-файл.|  
|[importidl](../windows/importidl.md)|Вставляет указанный IDL-файла в сгенерированный IDL-файл|  
|[importlib](../windows/importlib.md)|Делает типы, которые уже были скомпилированы в другую библиотеку типов, доступными для создаваемой библиотеки типов.|  
|[include](../windows/include-cpp.md)|Указывает один или несколько файлов заголовков, которые должны быть включены в сгенерированный IDL-файл.|  
|[includelib](../windows/includelib-cpp.md)|В результате файл IDL или .h, должны быть включены в сгенерированный IDL-файл.|  
|[library_block](../windows/library-block.md)|Помещает конструкцию внутри блока библиотеки IDL-файл.|  
|[Модуль](../windows/module-cpp.md)|Определяет блок библиотеки в IDL-файле.|  
|[no_injected_text](../windows/no-injected-text.md)|Запрещает компилятору встраивать код в результате использования атрибута.|  
|[pragma](../windows/pragma.md)|Создает указанную строку без символов кавычек, в сгенерированный IDL-файл.|  
  
## <a name="see-also"></a>См. также  
 [Список атрибутов по использованию](../windows/attributes-by-usage.md)