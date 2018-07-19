---
title: Преобразования назначений | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- conversions, assignment
- assignment conversions
ms.assetid: 4ee01013-de32-4aae-b12e-0051d0cde927
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 928f80375ecdd33902a0586cf31091d5764ee160
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32381838"
---
# <a name="assignment-conversions"></a>Преобразования назначений
В операциях присваивания тип присваиваемого значения преобразуется в тип переменной, которой присваивается значение. C позволяет при присваивании выполнять преобразования между целочисленными типами и типами с плавающей запятой даже в случае потери данных при преобразовании. Используемый метод преобразования зависит от того, какие типы участвуют в операции присваивания, как описано в статье [Обычные арифметические преобразования](../c-language/usual-arithmetic-conversions.md) и в следующих статьях.  
  
-   [Преобразования из целочисленных типов со знаком](../c-language/conversions-from-signed-integral-types.md)  
  
-   [Преобразования из целочисленных типов без знака](../c-language/conversions-from-unsigned-integral-types.md)  
  
-   [Преобразования типов с плавающей запятой](../c-language/conversions-from-floating-point-types.md)  
  
-   [Преобразования в типы указателей и из типов указателей](../c-language/conversions-to-and-from-pointer-types.md)  
  
-   [Преобразования из других типов](../c-language/conversions-from-other-types.md)  
  
 Квалификаторы типа не влияют на допустимость преобразования, но в левой части операции присваивания нельзя использовать левостороннее значение **const**.  
  
## <a name="see-also"></a>См. также  
 [Преобразования типов](../c-language/type-conversions-c.md)