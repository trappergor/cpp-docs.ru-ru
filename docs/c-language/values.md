---
title: Значения | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 24003f89-220f-4f93-be7a-b650c26157d7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8bef044535d2f5a5b337823b1798feaea48745d7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46106282"
---
# <a name="values"></a>Значения

**ANSI 3.1.2.5** Представления и наборы значений различных типов чисел с плавающей запятой

Тип **float** содержит 32 разряда: 1 для знака, 8 для экспоненты и 23 для мантиссы. Он имеет диапазон +/–3,4E38 с точностью не менее 7 знаков.

Тип **double** содержит 64 разряда: 1 для знака, 11 для экспоненты и 52 для мантиссы. Он имеет диапазон +/–1,7E308 с точностью не менее 15 знаков.

Тип **long double** содержит 80 разрядов: 1 для знака, 15 для экспоненты и 64 для мантиссы. Он имеет диапазон +/–1,2E4932 с точностью не менее 19 знаков. Обратите внимание на то, что в компиляторе Microsoft C тип **long double** имеет такое же представление, как и тип **double**.

## <a name="see-also"></a>См. также

[Вычисления с плавающей запятой](../c-language/floating-point-math.md)