---
title: Атрибуты интерфейса | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++], reference topics
- interface attributes
ms.assetid: 27fcdfee-abce-4585-8b53-ee31635356e8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8c61aeb0dcf3a9e0e001f89b9872b43b0af092b2
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42593327"
---
# <a name="interface-attributes"></a>Атрибуты интерфейса

Следующие атрибуты применяются к [interface (или __interface)](../cpp/interface.md) ключевым словом языка C++.

|Атрибут|Описание:|
|---------------|-----------------|
|[async_uuid](../windows/async-uuid.md)|Указывает UUID, компилятор MIDL определить синхронные и асинхронные версии COM-интерфейса.|
|[Custom](../windows/custom-cpp.md)|Позволяет определять собственные атрибуты.|
|[dispinterface](../windows/dispinterface.md)|Помещает интерфейс в IDL-файл в качестве интерфейса диспетчеризации.|
|[dual](../windows/dual.md)|Помещает интерфейс в IDL-файл как сдвоенный интерфейс.|
|[export](../windows/export.md)|В результате структуру данных, должно быть помещено в IDL-файла.|
|[helpcontext](../windows/helpcontext.md)|Указывает идентификатор контекста, который позволяет пользователю просматривать сведения об этом элементе в файле справки.|
|[helpfile](../windows/helpfile.md)|Задает имя файла справки для библиотеки типов.|
|[helpstring](../windows/helpstring.md)|Определяет строку символов, используемую для описания элемента, к которому оно применяется.|
|[helpstringcontext](../windows/helpstringcontext.md)|Указывает идентификатор раздела справки в файл с расширением .hlp или .chm.|
|[helpstringdll](../windows/helpstringdll.md)|Указывает имя библиотеки DLL для выполнения уточняющего запроса строки документа (локализации).|
|[hidden](../windows/hidden.md)|Указывает, что элемент существует, но не должен отображаться в пользовательском браузере.|
|[library_block](../windows/library-block.md)|Помещает конструкцию внутри блока библиотеки в IDL-файл.|
|[локальный](../windows/local-cpp.md)|Позволяет использовать в качестве генератор заголовка при использовании в заголовке интерфейс компилятора MIDL. При использовании в отдельной функции, обозначает локальной процедуры, для которого создаются без заглушек.|
|[nonextensible](../windows/nonextensible.md)|Указывает, что `IDispatch` реализация содержит только свойства и методы, перечисленных в описании интерфейса и не может быть расширен с помощью дополнительных членов во время выполнения. Этот атрибут действителен только на [двойной](../windows/dual.md) интерфейс.|
|[odl](../windows/odl.md)|Определяет интерфейс как интерфейс языка описания объекта (ODL).|
|[object](../windows/object-cpp.md)|Определяет пользовательский интерфейс.|
|[oleautomation](../windows/oleautomation.md)|Указывает, что интерфейс совместим со службой автоматизации.|
|[pointer_default](../windows/pointer-default.md)|Указывает атрибут указатель по умолчанию для всех указателей, за исключением верхнего уровня указателей, которые отображаются в списках параметров.|
|[ptr](../windows/ptr.md)|Определяет указатель как полный указатель.|
|[restricted](../windows/restricted.md)|Определяет, какие члены библиотеки не может вызываться произвольным образом.|
|[uuid](../windows/uuid-cpp-attributes.md)|Предоставляет уникальный идентификатор для библиотеки|

Необходимо соблюдать эти правила для определения интерфейса:

- Соглашение о вызовах по умолчанию — [__stdcall](../cpp/stdcall.md).

- Идентификатор GUID предоставляется для вас, если вы не предоставляете.

- Перегруженные методы не допускаются.

Если не указать [uuid](../windows/uuid-cpp-attributes.md) атрибута и с использованием имени интерфейса в проектах другой атрибут, создается одинаковый идентификатор GUID.

## <a name="see-also"></a>См. также

[Список атрибутов по использованию](../windows/attributes-by-usage.md)