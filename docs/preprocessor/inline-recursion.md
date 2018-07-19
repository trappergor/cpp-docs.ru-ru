---
title: inline_recursion | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- inline_recursion_CPP
- vc-pragma.inline_recursion
dev_langs:
- C++
helpviewer_keywords:
- pragmas, inline_recursion
- inline_recursion pragma
ms.assetid: cfef5791-63b7-45ac-9574-623747b9b9c9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f81347c8286dfa1f0651af43bd3134565a22aade
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33849500"
---
# <a name="inlinerecursion"></a>inline_recursion
Управляет развертыванием встроенного кода непосредственных или взаимных рекурсивных вызовов функций.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
#pragma inline_recursion( [{on | off}] )  
```  
  
## <a name="remarks"></a>Примечания  
 Используйте эту директиву #pragma для управления функциями, помеченными как [встроенного](../cpp/inline-functions-cpp.md) и [__inline](../cpp/inline-functions-cpp.md) или функции, автоматически развертываемыми компилятором при заданном параметре/Ob2. Для использования этой директивы #pragma требуется [/Ob](../build/reference/ob-inline-function-expansion.md) значения параметра компилятора 1 или 2. По умолчанию функция `inline_recursion` отключена. Эта директива #pragma действует начиная с первого после нее вхождения вызова функции и не влияет на определение функции.  
  
 Директива #pragma `inline_recursion` управляет развертыванием рекурсивных функций. Если параметр `inline_recursion` выключен и встроенная функция вызывает саму себя (прямо или косвенно), эта функция разворачивается только один раз. Если `inline_recursion` имеет значение on, функция разворачивается несколько раз, пока не достигнет значения, заданного с помощью [inline_depth](../preprocessor/inline-depth.md) pragma, значение по умолчанию для рекурсивных функций, которые определены в `inline_depth` pragma, или ограничение производительности .  
  
## <a name="see-also"></a>См. также  
 [Директивы pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)   
 [inline_depth](../preprocessor/inline-depth.md)   
 [/Ob (расширение встраиваемых функций)](../build/reference/ob-inline-function-expansion.md)