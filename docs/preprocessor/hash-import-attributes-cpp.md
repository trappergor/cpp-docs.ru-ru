---
title: '#Импорт атрибуты (C++) | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- '#import directive, attributes'
ms.assetid: 2a5085e3-82ee-4f83-892b-0aa6cc13863b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d1e69f977ffaacdfd2bb8bb0f53d3fe197af3fad
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33842292"
---
# <a name="import-attributes-c"></a>Атрибуты #import (C++)
Предоставляет ссылки на атрибуты, используемые с директивой #import.  
  
 **Блок, относящийся только к системам Microsoft**  
  
 Для директивы #import доступны следующие атрибуты.  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|[auto_rename](../preprocessor/auto-rename.md)|Переименовывает зарезервированные слова C++ путем добавления двух знаков подчеркивания (__) к именам переменных, чтобы разрешить потенциальные конфликты имен.|  
|[auto_search](../preprocessor/auto-search.md)|Указывает, что если на библиотеку типов ссылаются при помощи директивы #import, и при этом она сама ссылается на другую библиотеку типов, то компилятор может неявным образом выполнить директиву #import и для второй библиотеки типов.|  
|[embedded_idl](../preprocessor/embedded-idl.md)|Указывает, что библиотека типов записывается в файл .tlh с сохранением кода, созданного с атрибутами.|  
|[exclude](../preprocessor/exclude-hash-import.md)|Исключает элементы из создаваемых файлов заголовка библиотеки типов.|  
|[high_method_prefix](../preprocessor/high-method-prefix.md)|Задает префикс, используемый при именовании высокоуровневых свойств и методов.|  
|[high_property_prefixes](../preprocessor/high-property-prefixes.md)|Задает другие префиксы для трех методов свойств.|  
|[implementation_only](../preprocessor/implementation-only.md)|Отключает создание файла заголовка .tlh (основного файла заголовка).|  
|[include()](../preprocessor/include-parens.md)|Отключает автоматическое исключение.|  
|[inject_statement](../preprocessor/inject-statement.md)|Вставляет свой аргумент как исходный текст в заголовок библиотеки типов.|  
|[named_guids](../preprocessor/named-guids.md)|Указывает компилятору определять и инициализировать переменные GUID в старом стиле, в формате **LIBID_MyLib**, **CLSID_MyCoClass**, **IID_MyInterface**, и **DIID _MyDispInterface**.|  
|[no_auto_exclude](../preprocessor/no-auto-exclude.md)|Отключает автоматическое исключение.|  
|[no_dual_interfaces](../preprocessor/no-dual-interfaces.md)|Изменяет способ, которым компилятор создает функции оболочки для методов сдвоенных интерфейсов.|  
|[no_implementation](../preprocessor/no-implementation.md)|Отключает создание заголовка .tli, который содержит реализацию функций-членов оболочки.|  
|[no_namespace](../preprocessor/no-namespace.md)|Указывает, что пространство имен не генерируется компилятором.|  
|[no_registry](../preprocessor/no-registry.md)|Указывает компилятору не искать библиотеки типов в реестре.|  
|[no_search_namespace](../preprocessor/no-search-namespace.md)|Имеет ту же функциональность, что [no_namespace](../preprocessor/no-namespace.md) атрибута, но используется для библиотек типов, которые можно использовать директиву #import с [auto_search](../preprocessor/auto-search.md) атрибута.|  
|[no_smart_pointers](../preprocessor/no-smart-pointers.md)|Отключает создание интеллектуальных указателей для всех интерфейсов в библиотеке типов.|  
|[raw_dispinterfaces](../preprocessor/raw-dispinterfaces.md)|Указывает компилятору сгенерировать низкоуровневые функции оболочки для disp-интерфейса методов и свойств, которые вызывают **IDispatch::Invoke** и возвращают `HRESULT` код ошибки.|  
|[raw_interfaces_only](../preprocessor/raw-interfaces-only.md)|Подавляет создание функции-оболочки обработки ошибок и [свойство](../cpp/property-cpp.md) объявления, использующие эти функции-оболочки.|  
|[raw_method_prefix](../preprocessor/raw-method-prefix.md)|Указывает другой префикс, чтобы избежать конфликтов имен.|  
|[raw_native_types](../preprocessor/raw-native-types.md)|Отключает использование классов поддержки COM в высокоуровневых функциях оболочки и принудительно использует вместо них низкоуровневые типы данных.|  
|[raw_property_prefixes](../preprocessor/raw-property-prefixes.md)|Задает другие префиксы для трех методов свойств.|  
|[rename](../preprocessor/rename-hash-import.md)|Обходит проблемы конфликтов имен.|  
|[rename_namespace](../preprocessor/rename-namespace.md)|Переименовывает пространство имен, к которому относится содержимое библиотеки типов.|  
|[rename_search_namespace](../preprocessor/rename-search-namespace.md)|Имеет ту же функциональность, что [rename_namespace](../preprocessor/rename-namespace.md) атрибута, но используется для библиотек типов, которые можно использовать директиву #import с [auto_search](../preprocessor/auto-search.md) атрибута.|  
|[tlbid](../preprocessor/tlbid.md)|Позволяет загружать библиотеки, отличные от основной библиотеки типов.|  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [директива #import](../preprocessor/hash-import-directive-cpp.md)