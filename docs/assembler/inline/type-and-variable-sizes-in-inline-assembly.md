---
title: "Размеры типа и переменной во встроенной сборке | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- length
- Type
dev_langs: C++
helpviewer_keywords:
- variables, length
- size, getting in inline assembly
- size
- LENGTH operator
- TYPE operator
- SIZE operator
- inline assembly, operators
- variables, type
- variables, size
ms.assetid: b62c2f2b-a7ad-4145-bae4-d890db86d348
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ee9edf9430c0333317a767e8f8c114453a6d80f6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="type-and-variable-sizes-in-inline-assembly"></a>Размеры типа и переменной во встроенном коде на языке ассемблера
**Блок, относящийся только к системам Microsoft**  
  
 **Длина**, **размер**, и **тип** операторы имеют ограниченное значение во встроенной сборке. Их невозможно использовать с оператором `DUP` (поскольку невозможно определить данные с директивами или операторами MASM). Однако их можно использовать для поиска размера переменных или типов C либо C++.  
  
-   **Длина** оператор может возвращать число элементов в массиве. Он возвращает значение 1 для переменных, отличных от массива.  
  
-   **Размер** оператор может возвращать размер переменной C или C++. Размер переменной — это совокупность его **длина** и **ТИПА**.  
  
-   **Тип** оператор может возвращать размер типа C или C++ или переменной. Если переменная является массивом, **тип** возвращает размер отдельного элемента массива.  
  
 Например, если программа содержит массив `int`, состоящий из 8 элементов,  
  
```  
int arr[8];  
```  
  
 результатом следующих выражений C и сборки является размер массива `arr` и его элементов.  
  
|__asm|В|Размер|  
|-------------|-------|----------|  
|**Длина** arr|`sizeof`(arr)/`sizeof`(arr[0])|8|  
|**РАЗМЕР** arr|`sizeof`(arr)|32|  
|**Тип** arr|`sizeof`(arr[0])|4|  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Использование языка ассемблера в блоках __asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)