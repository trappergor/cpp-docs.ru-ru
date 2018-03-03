---
title: "Числовой (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- <cliext/numeric>
dev_langs:
- C++
helpviewer_keywords:
- numeric functions [STL/CLR]
- <cliext/numeric> header [STL/CLR]
- <numeric> header [STL/CLR]
ms.assetid: 1dc4d9a3-e734-459c-9678-5d9be0ef4c79
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: cdf9ccb65299af688fde2fbff7b3d6cedad6de96
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="numeric-stlclr"></a>числовой (STL/CLR)
Определяет шаблонные функции контейнера, которые выполняют алгоритмы, предоставляемые для числовой обработки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#include <cliext/numeric>  
```  
  
## <a name="functions"></a>Функции  
  
|Функция|Описание:|  
|--------------|-----------------|  
|[accumulate (STL/CLR)](../dotnet/accumulate-stl-clr.md)|Вычисляет сумму всех элементов в указанном диапазоне, включая некоторое начальное значение, путем вычисления последовательных частичных сумм или вычисляет результат последовательных частичных сумм, аналогичным образом полученных от использования указанной бинарной операции, отличной от суммы.|  
|[adjacent_difference (STL/CLR)](../dotnet/adjacent-difference-stl-clr.md)|Вычисляет последовательные различия между каждым элементом и его предшественником в диапазоне ввода и выводит результаты в диапазон назначения или вычисляет результат обобщенной процедуры, где операция разности заменена другой определенной бинарной операцией.|  
|[inner_product (STL/CLR)](../dotnet/inner-product-stl-clr.md)|Вычисляет сумму поэлементного умножения двух диапазонов и добавляет ее к указанному начальному значению либо вычисляет результат обобщенной процедуры, где бинарные операции суммы и умножения заменены на другие указанные бинарные операции.|  
|[partial_sum (STL/CLR)](../dotnet/partial-sum-stl-clr.md)|Вычисляет ряд сумм в диапазоне ввода с первого элемента и до `i`элемент th и сохраняет результат каждой такой суммы в `i`-ый элемент диапазон назначения или вычисляет результат обобщенной процедуры, где операции суммы заменяется на другой указанной бинарной операции.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/numeric >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [Справочник по библиотеке STL/CLR](../dotnet/stl-clr-library-reference.md)