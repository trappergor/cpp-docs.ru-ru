---
title: "Ошибка компилятора C3397 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3397
dev_langs:
- C++
helpviewer_keywords:
- C3397
ms.assetid: a8536e87-79c4-4ed7-bd96-42704d06391f
caps.latest.revision: 5
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
ms.openlocfilehash: c94d2e186112f2112c20f12af487993ce9080fbb
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3397"></a>Ошибка компилятора C3397
Агрегатная инициализация не допускается в аргументах по умолчанию  
  
 Массив был объявлен неправильно.  В разделе [массивы](../../windows/arrays-cpp-component-extensions.md) для получения дополнительной информации.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C3397:  
  
```  
// C3397.cpp  
// compile with: /clr  
// /clr /c  
void Func(array<int> ^p = gcnew array<int> { 1, 2, 3 });   // C3397  
void Func2(array<int> ^p = gcnew array<int> (3));   // OK  
  
int main() {  
   array<int> ^p = gcnew array<int> { 1, 2, 3};   // OK  
}  
```
