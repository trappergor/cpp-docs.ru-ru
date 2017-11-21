---
title: "Ошибка компилятора C2687 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2687
dev_langs: C++
helpviewer_keywords: C2687
ms.assetid: 1d24b24a-cd0f-41cc-975c-b08dcfb7f402
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6e74167bcc9637d2d9f0c39d0d3d36f960db5efa
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2687"></a>Ошибка компилятора C2687
«Тип»: объявление исключения не может быть «void» и не может обозначать неполный тип, указатель или ссылку на неполный тип  
  
 Для типа частью объявления исключения он должен быть определен и не пустой.  
  
 Следующий пример приводит к возникновению ошибки C2687:  
  
```  
// C2687.cpp  
class C;  
  
int main() {  
   try {}  
   catch (C) {}   // C2687 error  
}  
```  
  
 Возможное решение:  
  
```  
// C2687b.cpp  
// compile with: /EHsc  
class C {};  
  
int main() {  
   try {}  
   catch (C) {}  
}  
```