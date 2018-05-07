---
title: Ключевое слово Auto | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 744a41c0-2510-4140-a1be-96257e722908
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 93b2f5e28dc0306a996b4c8bdb799122fe4646ab
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="auto-keyword"></a>Ключевое слово auto
Ключевое слово `auto` является описателем объявления. Однако стандарт языка C++ определяет первоначальное и измененное значение данного ключевого слова. До Visual C++ 2010 `auto` ключевое слово объявляло переменную в *автоматического* класса хранения, то есть переменную с локальным временем существования. Начиная с Visual C++ 2010 `auto` ключевое слово объявляет переменную, тип которой выводится из выражения инициализации в его объявлении. [/Zc: auto&#91;-&#93; ](../build/reference/zc-auto-deduce-variable-type.md) параметр компилятора контролирует значение `auto` ключевое слово.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
auto declarator ;  
auto declarator initializer;  
```  
  
## <a name="remarks"></a>Примечания  
 Определение ключевого слова `auto` меняется в языке программирования C++, но не в С.  
  
 В следующих разделах описывается ключевое слово `auto` и соответствующий параметр компилятора:  
  
-   [Auto](../cpp/auto-cpp.md) описывается новое определение `auto` ключевое слово.  
  
  
-   [/ Zc: auto (выведение типа переменной)](../build/reference/zc-auto-deduce-variable-type.md) описание параметра компилятора, который сообщает компилятору, определение которого `auto` ключевое слово для использования.  
  
## <a name="see-also"></a>См. также  
 [Ключевые слова](../cpp/keywords-cpp.md)