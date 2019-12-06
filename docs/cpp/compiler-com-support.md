---
title: Поддержка COM компилятора
ms.date: 05/06/2019
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 76a78442-f2a4-4985-9967-67e20773f847
ms.openlocfilehash: 6ab697e5a090158b034a385e60978cff4a73f488
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857584"
---
# <a name="compiler-com-support"></a>Поддержка COM компилятора

**Блок, относящийся только к системам Майкрософт**

Компилятор Майкрософт C++ может напрямую считывать библиотеки типов модели COM и переводить содержимое в C++ исходный код, который может быть добавлен в компиляцию. Расширения языка доступны для упрощения программирования COM на стороне клиента для классических приложений.

С помощью [директивы препроцессора #import](../preprocessor/hash-import-directive-cpp.md)компилятор может прочитать библиотеку типов и преобразовать ее в файл C++ заголовка, описывающий COM-интерфейсы в качестве классов. Набор атрибутов `#import` доступен для пользовательского контроля содержимого в полученных файлах заголовка библиотеки типов.

Можно использовать идентификатор [UUID](../cpp/uuid-cpp.md) расширенного атрибута [__declspec](../cpp/declspec.md) , чтобы назначить глобально уникальный идентификатор (GUID) для COM-объекта. Ключевое слово [__uuidof](../cpp/uuidof-operator.md) можно использовать для извлечения идентификатора GUID, связанного с COM-объектом. Другой атрибут **__declspec** , [свойство](../cpp/property-cpp.md), может использоваться для указания `get` и `set` методов для элемента данных COM-объекта.

Набор функций COM поддерживает глобальные функции и классы, предназначенные для поддержки типов `VARIANT` и `BSTR`, реализации смарт-указателей и инкапсуляции объекта ошибки, созданного `_com_raise_error`:

- [Глобальные функции COM-модели компилятора](../cpp/compiler-com-global-functions.md)

- [_bstr_t](../cpp/bstr-t-class.md)

- [_com_error](../cpp/com-error-class.md)

- [_com_ptr_t](../cpp/com-ptr-t-class.md)

- [_variant_t](../cpp/variant-t-class.md)

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также:

[Классы поддержки модели COM компилятора](../cpp/compiler-com-support-classes.md)<br/>
[Глобальные функции COM-модели компилятора](../cpp/compiler-com-global-functions.md)
