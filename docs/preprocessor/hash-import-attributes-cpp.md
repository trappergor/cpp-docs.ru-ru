---
title: '#импортировать атрибуты (C++)'
ms.date: 11/04/2016
helpviewer_keywords:
- '#import directive, attributes'
ms.assetid: 2a5085e3-82ee-4f83-892b-0aa6cc13863b
ms.openlocfilehash: 954dfec50db75c0e3d11f0924b0ee398cd211fe1
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59036144"
---
# <a name="import-attributes-c"></a>Атрибуты #import (C++)
Ссылки на атрибуты, используемые с `#import` директива.

**Блок, относящийся только к системам Microsoft**

Доступны следующие атрибуты для `#import` директива.

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
|[named_guids](../preprocessor/named-guids.md)|Указывает компилятору определять и инициализировать переменные GUID в старом стиле, в форме `LIBID_MyLib`, `CLSID_MyCoClass`, `IID_MyInterface`, и `DIID_MyDispInterface`.|
|[no_auto_exclude](../preprocessor/no-auto-exclude.md)|Отключает автоматическое исключение.|
|[no_dual_interfaces](../preprocessor/no-dual-interfaces.md)|Изменяет способ, которым компилятор создает функции оболочки для методов сдвоенных интерфейсов.|
|[no_implementation](../preprocessor/no-implementation.md)|Отключает создание заголовка .tli, который содержит реализацию функций-членов оболочки.|
|[no_namespace](../preprocessor/no-namespace.md)|Указывает, что пространство имен не генерируется компилятором.|
|[no_registry](../preprocessor/no-registry.md)|Указывает компилятору не искать библиотеки типов в реестре.|
|[no_search_namespace](../preprocessor/no-search-namespace.md)|Имеет ту же функциональность, что [no_namespace](../preprocessor/no-namespace.md) атрибут, однако применяется для библиотек типов, которые можно использовать директиву #import с [auto_search](../preprocessor/auto-search.md) атрибута.|
|[no_smart_pointers](../preprocessor/no-smart-pointers.md)|Отключает создание интеллектуальных указателей для всех интерфейсов в библиотеке типов.|
|[raw_dispinterfaces](../preprocessor/raw-dispinterfaces.md)|Указывает компилятору сгенерировать низкоуровневые функции оболочки для методов disp-интерфейса и свойства, которые вызывают `IDispatch::Invoke` и возвращают код ошибки HRESULT.|
|[raw_interfaces_only](../preprocessor/raw-interfaces-only.md)|Отключает создание функций оболочки обработки ошибок и [свойство](../cpp/property-cpp.md) объявления, в которых используются такие функции оболочки.|
|[raw_method_prefix](../preprocessor/raw-method-prefix.md)|Указывает другой префикс, чтобы избежать конфликтов имен.|
|[raw_native_types](../preprocessor/raw-native-types.md)|Отключает использование классов поддержки COM в высокоуровневых функциях оболочки и принудительно использует вместо них низкоуровневые типы данных.|
|[raw_property_prefixes](../preprocessor/raw-property-prefixes.md)|Задает другие префиксы для трех методов свойств.|
|[rename](../preprocessor/rename-hash-import.md)|Обходит проблемы конфликтов имен.|
|[rename_namespace](../preprocessor/rename-namespace.md)|Переименовывает пространство имен, к которому относится содержимое библиотеки типов.|
|[rename_search_namespace](../preprocessor/rename-search-namespace.md)|Имеет ту же функциональность, что [rename_namespace](../preprocessor/rename-namespace.md) атрибут, однако применяется для библиотек типов, которые можно использовать директиву #import с [auto_search](../preprocessor/auto-search.md) атрибута.|
|[tlbid](../preprocessor/tlbid.md)|Позволяет загружать библиотеки, отличные от основной библиотеки типов.|

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[директива #import](../preprocessor/hash-import-directive-cpp.md)