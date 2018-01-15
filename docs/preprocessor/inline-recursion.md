---
title: "inline_recursion | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- inline_recursion_CPP
- vc-pragma.inline_recursion
dev_langs: C++
helpviewer_keywords:
- pragmas, inline_recursion
- inline_recursion pragma
ms.assetid: cfef5791-63b7-45ac-9574-623747b9b9c9
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d749753e7eaf81284de72314f5f940fd2790962c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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