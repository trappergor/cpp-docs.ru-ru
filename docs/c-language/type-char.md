---
title: Тип char
ms.date: 11/04/2016
helpviewer_keywords:
- type char
- unsigned char keyword [C]
- char keyword [C]
ms.assetid: a5da0866-e780-4793-be87-15a8426e7ea0
ms.openlocfilehash: c0524d30e19f8b54f577216a3160f721cbd2f0e8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50551064"
---
# <a name="type-char"></a>Тип char

Тип `char` используется для хранения целочисленного значения члена представительной кодировки. Целочисленное значение — это код ASCII, соответствующий указанному символу.

**Блок, относящийся только к системам Microsoft**

Значения символов типа `unsigned char` находятся в диапазоне от 0 до 0xFF по шестнадцатеричной системе счисления. **signed char** имеет диапазон от 0x80 до 0x7F. Эти диапазоны преобразуются в диапазоны от 0 до 255 и от -128 до +127 по десятичной системе счисления соответственно. Параметр компилятора /J меняет используемый по умолчанию вариант: вместо **signed** устанавливается `unsigned`.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Хранение базовых типов](../c-language/storage-of-basic-types.md)