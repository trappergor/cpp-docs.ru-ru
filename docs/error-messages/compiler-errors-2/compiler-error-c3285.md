---
title: "Ошибка компилятора C3285 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3285
dev_langs:
- C++
helpviewer_keywords:
- C3285
ms.assetid: 04e8f210-d67e-4810-b153-e1efe2986c8f
caps.latest.revision: 6
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
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 5fde3d0a9ec1126ec7c078ccd76c309a2184ecf9
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3285"></a>Ошибка компилятора C3285
Оператор for each не может работать с переменными типа "тип"  
  
 Оператор `for each` повторяет группу встроенных операторов для каждого элемента в массиве или коллекции объектов.  
  
 В разделе [для каждой из них, в](../../dotnet/for-each-in.md) для получения дополнительной информации.  
  
## <a name="example"></a>Пример  
 При компиляции следующего примера возникнет ошибка C3285.  
  
```  
// C3285.cpp  
// compile with: /clr  
int main() {  
   for each (int i in 0) {}   // C3285   
  
   array<int> ^p = { 1, 2, 3 };  
   for each (int j in p) {}   // OK  
}  
```
