---
title: noinline | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- noinline_cpp
dev_langs:
- C++
helpviewer_keywords:
- noinline __declspec keyword
- __declspec keyword [C++], noinline
ms.assetid: f259d55b-dec7-4bde-8cf9-14521e4fdc42
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 37098e904402a42f6ff28e594db265fc07b4d458
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2018
ms.locfileid: "37944555"
---
# <a name="noinline"></a>noinline
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft  
 **__declspec(noinline)** указывает компилятору не функция-член (функция в классе).  
  
 Запрещать использовать функцию как встроенную имеет смысл, если она небольшая и не оказывает критического влияния на производительность кода. То есть, если функция небольшая и вряд ли будет вызываться часто (например, функция, которая обрабатывает условие ошибки).  
  
 Имейте в виду, что если функция отмечена **noinline**, вызывающая функция будет уменьшается и она сама является кандидатом для встраивания компилятором.  
  
```cpp 
class X {  
   __declspec(noinline) int mbrfunc() {  
      return 0;   
   }   // will not inline  
};  
```  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [__declspec](../cpp/declspec.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)   
 [inline, __inline, \__forceinline](inline-functions-cpp.md)

