---
title: Типы значений и их режимы работы (C + +/ CLI) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- value types
ms.assetid: 5cb872a6-1e0a-429d-853d-df4ab47e8f2a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4d2d980e48a6f948c35faf0c4e42969795ef8dc7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46404661"
---
# <a name="value-types-and-their-behaviors-ccli"></a>Типы значений и их режимы работы (C++/CLI)

Типы значений изменились различными способами — от управляемых расширений для C++ в Visual C++. В этом разделе мы рассмотрим тип перечисления CLR, а также тип класса значение вместе с упаковкой-преобразованием, а также доступ к экземпляру, упакованный в куче среды CLR, а также рассмотрим внутренних и закрепляющих указателей. В этой области будут внесены изменения обширный язык.

## <a name="in-this-section"></a>В этом разделе

[Тип перечисления Enum в среде CLR](../dotnet/value-types-and-their-behaviors-cpp-cli.md)<br/>
Рассматриваются изменения в объявлении и поведение для перечислений.

[Неявная упаковка-преобразование типов значений](../dotnet/implicit-boxing-of-value-types.md)<br/>
Описание причины неявная упаковка-преобразование типов значений и последующие изменения в поведении.

[Дескриптор отслеживания для упакованных значений](../dotnet/a-tracking-handle-to-a-boxed-value.md)<br/>
Рассматривается как неявная упаковка-преобразование преобразования типов значения для дескриптор отслеживания для упакованных значений объекта.

[Семантика типа значения](../dotnet/value-type-semantics.md)<br/>
Рассматриваются изменения в семантике типа значения, включая унаследованные виртуальные методы, конструкторы класса по умолчанию, внутренних указателей и закрепляющие указатели.

## <a name="see-also"></a>См. также

[Основы миграции C++/CLI](../dotnet/cpp-cli-migration-primer.md)<br/>
[Классы и структуры](../windows/classes-and-structs-cpp-component-extensions.md)