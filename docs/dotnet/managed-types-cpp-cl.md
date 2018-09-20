---
title: Управляемые типы (C++-CL) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- __gc types
- types [C++], CLR
ms.assetid: 1ddd114e-be02-4de7-a4dd-a2d72ad8ff81
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 382228b9e8364d90d7929b4633744071c5eb0c77
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46408046"
---
# <a name="managed-types-ccl"></a>Управляемые типы (C++/CL)

Синтаксис для объявления управляемых типов, а также создания и использования объектов этих типов претерпел значительные изменения из управляемых расширений для C++ в Visual C++. Это было сделано для повышения уровня их интеграцию в системе типов ISO-C++. Подробно в следующих подразделах описаны эти изменения.

## <a name="in-this-section"></a>В этом разделе

[Объявление управляемых типов классов](../dotnet/declaration-of-a-managed-class-type.md)<br/>
Описывается объявление управляемого `class`, `struct`, или `interface`.

[Объявление объекта ссылочного класса в среде CLR](../dotnet/declaration-of-a-clr-reference-class-object.md)<br/>
В этой статье описывается объявление объекта ссылочного класса типа с помощью дескриптора отслеживания.

[Объявление массива CLR](../dotnet/declaration-of-a-clr-array.md)<br/>
Объясняется, как объявить и инициализировать массив.

[Изменения в последовательности инициализации конструктора](../dotnet/changes-in-constructor-initialization-order.md)<br/>
Рассматриваются основные изменения в последовательности инициализации конструктора класса.

[Изменения в семантике деструктора](../dotnet/changes-in-destructor-semantics.md)<br/>
Рассматривается неопределенное завершение `Finalize` и `Dispose`, влияние на ссылаться на объекты, а также использование явного `Finalize`.

**Примечание:** обсуждение делегатов откладывается до [делегаты и события](../dotnet/delegates-and-events.md) для представления их с членами события внутри класса, общие принципы [объявления членов в пределах класса или интерфейса (C + +/ CLI) ](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md).

## <a name="see-also"></a>См. также

[Основы миграции C++/CLI](../dotnet/cpp-cli-migration-primer.md)<br/>
[Классы и структуры](../windows/classes-and-structs-cpp-component-extensions.md)<br/>
[Массивы](../windows/arrays-cpp-component-extensions.md)