---
title: Преобразования присваиваний
ms.date: 11/04/2016
helpviewer_keywords:
- conversions, assignment
- assignment conversions
ms.assetid: 4ee01013-de32-4aae-b12e-0051d0cde927
ms.openlocfilehash: cc75bdd8227c09247f6d4270f1fc21235de2eb05
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87211844"
---
# <a name="assignment-conversions"></a>Преобразования присваиваний

В операциях присваивания тип присваиваемого значения преобразуется в тип переменной, которой присваивается значение. C позволяет при присваивании выполнять преобразования между целочисленными типами и типами с плавающей запятой даже в случае потери данных при преобразовании. Используемый метод преобразования зависит от того, какие типы участвуют в операции присваивания, как описано в статье [Обычные арифметические преобразования](../c-language/usual-arithmetic-conversions.md) и в следующих статьях.

- [Преобразования из целочисленных типов со знаком](../c-language/conversions-from-signed-integral-types.md)

- [Преобразования из целочисленных типов без знака](../c-language/conversions-from-unsigned-integral-types.md)

- [Преобразования типов с плавающей запятой](../c-language/conversions-from-floating-point-types.md)

- [Преобразования в типы указателей и из типов указателей](../c-language/conversions-to-and-from-pointer-types.md)

- [Преобразования из других типов](../c-language/conversions-from-other-types.md)

Квалификаторы типа не влияют на допустимость преобразования, но в левой части операции присваивания нельзя использовать l-значение **`const`** .

## <a name="see-also"></a>См. также

[Преобразования типов](../c-language/type-conversions-c.md)
