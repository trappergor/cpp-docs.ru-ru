---
title: Усечение значений с плавающей запятой | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- floating-point numbers, truncation
ms.assetid: 051a6e22-c636-4af8-9ac4-40160f4affca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b30700b52e7cbbbc295d6050b03283b4b45a0b08
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46103819"
---
# <a name="truncation-of-floating-point-values"></a>Усечение значений с плавающей запятой

**ANSI 3.2.1.4** Направление усечения или округления при преобразовании числа с плавающей запятой в формат с плавающей запятой меньшего размера

Когда возникает потеря значимости, значение переменной с плавающей запятой округляется вниз до нуля. Потеря значимости может вызвать ошибку времени выполнения или привести к созданию непредсказуемого значения, в зависимости от указанных оптимизаций.

## <a name="see-also"></a>См. также

[Вычисления с плавающей запятой](../c-language/floating-point-math.md)