---
title: inline_depth | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- inline_depth_CPP
- vc-pragma.inline_depth
dev_langs:
- C++
helpviewer_keywords:
- pragmas, inline_depth
- inline_depth pragma
ms.assetid: 2bba60fe-43ea-4d09-90f7-aafaba3bad07
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e40b9382abc8ee0fa0c003964eebe75bc075e473
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="inlinedepth"></a>inline_depth
Задает глубину эвристического поиска для подстановки функций, то есть на глубине (в графе вызовов) больше `n` подстановка функций не выполняется.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
#pragma inline_depth( [n] )  
```  
  
## <a name="remarks"></a>Примечания  
 Эта директива pragma управляет подстановкой функций, помеченных [встроенного](../cpp/inline-functions-cpp.md) и [__inline](../cpp/inline-functions-cpp.md) или также автоматически параметре/Ob2.  
  
 Значение `n` может находиться в диапазоне от 0 до 255. Значение 255 означает, что глубина в диаграмме вызовов не ограничена, а 0 блокирует подстановку функций.  Если атрибут `n` не задан, используется значение по умолчанию (254).  
  
 **Inline_depth** pragma определяет, сколько раз будет развернута серия вызовов функций. Например, если глубина подстановки равна 4, и при этом функция A вызывает B, а затем B вызывает C, то все 3 вызова будут развернуты для подстановки. Однако если ближайшая глубина развертывания подставляемых функций равна двум, то развернуты будут только функции A и B, а C останется вызовом функции.  
  
 Для использования этой директивы pragma необходимо указать параметр компилятора /Ob со значением 1 или 2. Глубина, установленная при помощи этой директивы #pragma, начинает действовать с первого вызова функции, расположенной после директивы.  
  
 При выполнении расширения глубина подстановки может уменьшаться, но не увеличиваться. Если глубина подстановки равна 6, и при выполнении расширения препроцессор встречает **inline_depth** директиву pragma значение 8, глубина остается шесть.  
  
 **Inline_depth** pragma не оказывает влияния на функций, помеченных атрибутом `__forceinline`.  
  
> [!NOTE]
>  Подстановка для рекурсивных функций выполняется на глубину не более 16 вызовов.  
  
## <a name="see-also"></a>См. также  
 [Директивы pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)   
 [inline_recursion](../preprocessor/inline-recursion.md)