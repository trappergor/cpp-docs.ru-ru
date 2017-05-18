---
title: "Неустранимая ошибка C1016 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1016
dev_langs:
- C++
helpviewer_keywords:
- C1016
ms.assetid: 33f45c3e-2d8f-43ad-a445-c412d1d54ce1
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: b7f9a620f3df21a737736fce943ee750c7171387
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="fatal-error-c1016"></a>Неустранимая ошибка C1016
\#Ожидался ifdef идентификатор; #ifndef ожидается идентификатор  
  
 Директивы условной компиляции ([#ifdef](../../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md) или `#ifndef`) не имеет идентификатора для оценки. Чтобы устранить эту ошибку, необходимо указать идентификатор.  
  
 Следующий пример приводит к возникновению ошибки C1016:  
  
```  
// C1016.cpp  
#ifdef   // C1016  
#define FC1016  
#endif  
  
int main() {}  
```  
  
 Возможное решение  
  
```  
// C1016b.cpp  
#ifdef X  
#define FC1016  
#endif  
  
int main() {}  
```
