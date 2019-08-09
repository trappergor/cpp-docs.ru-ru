---
title: Поддержка COM компилятора
ms.date: 05/06/2019
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 76a78442-f2a4-4985-9967-67e20773f847
ms.openlocfilehash: 421930088dcbf9762d50b5af37d994b9008890eb
ms.sourcegitcommit: 720b74dddb1cdf4e570d55103158304ee1df81f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2019
ms.locfileid: "68606375"
---
# <a name="compiler-com-support"></a>Поддержка COM компилятора

## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft

Компилятор Майкрософт C++ может напрямую считывать библиотеки типов модели COM и переводить содержимое в C++ исходный код, который может быть добавлен в компиляцию. Расширения языка доступны для упрощения программирования COM на стороне клиента для классических приложений.

С помощью директивы препроцессора [#import](../preprocessor/hash-import-directive-cpp.md)компилятор может прочитать библиотеку типов и преобразовать ее в файл C++ заголовка, описывающий COM-интерфейсы в качестве классов. Набор атрибутов `#import` доступен для пользовательского контроля содержимого в полученных файлах заголовка библиотеки типов.

Можно использовать идентификатор [UUID](../cpp/uuid-cpp.md) расширенного атрибута [__declspec](../cpp/declspec.md) , чтобы назначить глобально уникальный идентификатор (GUID) для COM-объекта. Ключевое слово [__uuidof](../cpp/uuidof-operator.md) можно использовать для извлечения идентификатора GUID, связанного с COM-объектом. Другой атрибут **__declspec** , [свойство](../cpp/property-cpp.md), может использоваться `get` для указания методов и `set` для элемента данных COM-объекта.

Набор функций com поддерживает глобальные функции и классы, предназначенные для поддержки `VARIANT` типов и `BSTR` , реализации смарт-указателей и инкапсуляции объекта Error, вызываемого: `_com_raise_error`

- [Глобальные функции COM-модели компилятора](../cpp/compiler-com-global-functions.md)

- [_bstr_t](../cpp/bstr-t-class.md)

- [_com_error](../cpp/com-error-class.md)

- [_com_ptr_t](../cpp/com-ptr-t-class.md)

- [_variant_t](../cpp/variant-t-class.md)

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Классы поддержки модели COM компилятора](../cpp/compiler-com-support-classes.md)<br/>
[Глобальные функции COM-модели компилятора](../cpp/compiler-com-global-functions.md)
