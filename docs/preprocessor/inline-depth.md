---
title: inline_depth | Документация Майкрософт
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
ms.openlocfilehash: cbb90d36ea3da8e443eede8a3d74a35246077d52
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46410273"
---
# <a name="inlinedepth"></a>inline_depth
Указывает глубину, эвристического поиска таким образом, что функция не будет встроенным, то есть на глубине (в графе вызовов) больше, чем *n*.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#pragma inline_depth( [n] )  
```  
  
## <a name="remarks"></a>Примечания  
 
Эта директива pragma управляет подстановкой функций с пометкой [встроенного](../cpp/inline-functions-cpp.md) и [__inline](../cpp/inline-functions-cpp.md) также автоматически `/Ob2` параметр.  
  
*n* может иметь значение от 0 до 255, 255 означает, что глубина в графе вызовов, куда ноль подавляет Подстановка.  Когда *n* не указан, используется значение по умолчанию (254).  
  
**Inline_depth** директива pragma управляет количество раз, можно развернуть, ряд вызовов функций. Например, если глубина подстановки равна 4, и при этом функция A вызывает B, а затем B вызывает C, то все 3 вызова будут развернуты для подстановки. Однако если ближайшая глубина развертывания подставляемых функций равна двум, то развернуты будут только функции A и B, а C останется вызовом функции.  
  
Чтобы использовать эту директиву pragma, необходимо задать `/Ob` параметр компилятора 1 или 2. Глубина, установленная при помощи этой директивы #pragma, начинает действовать с первого вызова функции, расположенной после директивы.  
  
При выполнении расширения глубина подстановки может уменьшаться, но не увеличиваться. Если глубина подстановки равна 6, и при выполнении расширения препроцессор встречает **inline_depth** со значением из восьми глубина остается шесть.  
  
**Inline_depth** директива pragma не влияет на функции, помеченные с помощью `__forceinline`.  
  
> [!NOTE]
> Подстановка для рекурсивных функций выполняется на глубину не более 16 вызовов.  
  
## <a name="see-also"></a>См. также  
 
[Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)<br/>
[inline_recursion](../preprocessor/inline-recursion.md)