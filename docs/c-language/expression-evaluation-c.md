---
title: "Вычисление выражений (C) | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- expression evaluation
- expressions [C++], evaluating
ms.assetid: 9493f8cc-64a2-4284-9aaf-26eec11c4f40
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9984444bd7de3144cb1e81ddb527c68531a9d7d6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="expression-evaluation-c"></a>Вычисление выражений (C)
Выражения, включающие назначение, унарный инкремент, унарный декремент или вызов функции, могут случайно оказать воздействие на вычисление (побочные эффекты). При достижении точки последовательности вычисление всех элементов, расположенных до нее, включая все побочные эффекты, гарантированно завершается до начала вычисления любого элемента после точки последовательности.  
  
 Побочные эффекты — это изменения, вызванные вычислением выражения. Побочные эффекты возникают при изменении значения переменной в результате вычисления выражения. Все операции присваивания имеют побочные эффекты. Вызовы функций также могут иметь побочные эффекты, если при этом изменяется значение видимого снаружи элемента в результате явного назначения или косвенного назначения с помощью указателя.  
  
## <a name="see-also"></a>См. также  
 [Операнды и выражения](../c-language/operands-and-expressions.md)