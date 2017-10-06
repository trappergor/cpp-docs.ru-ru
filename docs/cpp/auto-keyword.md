---
title: "Ключевое слово Auto | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- auto_cpp
dev_langs:
- C++
helpviewer_keywords:
- automatic storage class, auto keyword
- auto keyword
ms.assetid: 744a41c0-2510-4140-a1be-96257e722908
caps.latest.revision: 14
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 0413fd47b486cf1613b7c249b93e6a3507a5577c
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="auto-keyword"></a>Ключевое слово auto
Ключевое слово `auto` является описателем объявления. Однако стандарт языка C++ определяет первоначальное и измененное значение данного ключевого слова. До Visual C++ 2010 `auto` ключевое слово объявляло переменную в *автоматического* класса хранения, то есть переменную с локальным временем существования. Начиная с Visual C++ 2010 `auto` ключевое слово объявляет переменную, тип которой выводится из выражения инициализации в его объявлении. [/Zc: auto &#91;-&#93;](../build/reference/zc-auto-deduce-variable-type.md) параметр компилятора контролирует значение `auto` ключевое слово.  
  
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
