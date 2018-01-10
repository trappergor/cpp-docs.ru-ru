---
title: "Значения | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 24003f89-220f-4f93-be7a-b650c26157d7
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ea979083fb00d57e455b97c2f6b94f7ea7c6b596
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="values"></a>Значения
**ANSI 3.1.2.5** Представления и наборы значений различных типов чисел с плавающей запятой  
  
 Тип **float** содержит 32 разряда: 1 для знака, 8 для экспоненты и 23 для мантиссы. Он имеет диапазон +/–3,4E38 с точностью не менее 7 знаков.  
  
 Тип **double** содержит 64 разряда: 1 для знака, 11 для экспоненты и 52 для мантиссы. Он имеет диапазон +/–1,7E308 с точностью не менее 15 знаков.  
  
 Тип **long double** содержит 80 разрядов: 1 для знака, 15 для экспоненты и 64 для мантиссы. Он имеет диапазон +/–1,2E4932 с точностью не менее 19 знаков. Обратите внимание на то, что в компиляторе Microsoft C тип **long double** имеет такое же представление, как и тип **double**.  
  
## <a name="see-also"></a>См. также  
 [Вычисления с плавающей запятой](../c-language/floating-point-math.md)