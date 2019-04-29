---
title: Грамматика выражения __based
ms.date: 11/04/2016
helpviewer_keywords:
- based addressing
ms.assetid: a68ff750-c7fa-4c0c-8d5f-2df76e4686c5
ms.openlocfilehash: 8dec9b0bcc7db25e2ec4c39b9d907922691bfc05
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393952"
---
# <a name="based-grammar"></a>Грамматика выражения __based

## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft

Базовая адресация полезна, когда требуется точный контроль над сегментом, в котором выделяются объекты (статические и динамические данные).

Единственной формой адресации допустимой в 32-разрядных и 64-разрядных компиляциях «основана на указатель», которая определяет тип, содержащий смещением 32-разрядной или 64-разрядная на 32-разрядная или 64-разрядных базовую или на основе **void**.

## <a name="grammar"></a>Грамматика

*based-range-modifier*: **__based(**  *base-expression*  **)**

*базовому выражению*: *based-variablebased-abstract-declaratorsegment-namesegment-cast*

*на основе переменной*: *идентификатор*

*на основе абстрактный декларатор*: *абстрактный декларатор*

*базового типа*: *имя типа*

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Относительные указатели](../cpp/based-pointers-cpp.md)