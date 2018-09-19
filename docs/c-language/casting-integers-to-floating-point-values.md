---
title: Приведение целочисленных значений к значениям с плавающей запятой | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- integers, casting to floating-point values
ms.assetid: 81fd5b7d-15eb-4c11-a8c8-e1621ff54fd3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a81b72a7dfedbc1d6033d53bde63be22943abb08
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46055225"
---
# <a name="casting-integers-to-floating-point-values"></a>Приведение целочисленных значений к значениям с плавающей запятой

**ANSI 3.2.1.3** Направление усечения при преобразовании целого числа в число с плавающей запятой, которое не может точно представить исходное значение

Если целое число приводится к значению с плавающей запятой, которое точно не может представить это значение, это значение округляется (в большую или меньшую сторону) до ближайшего подходящего значения.

Например, приведение числа типа **unsigned long** (точность — 32 бита) к числу типа **float** (мантисса которого имеет точность 23 бита) приводит к округлению числа до ближайшего кратного 256. Значения **long** в диапазоне от 4 294 966 913 до 4 294 967 167 округляются до значения 4 294 967 040 с типом **float**.

## <a name="see-also"></a>См. также

[Вычисления с плавающей запятой](../c-language/floating-point-math.md)