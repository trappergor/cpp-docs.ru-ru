---
title: "Ошибка компилятора C2951 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2951
dev_langs:
- C++
helpviewer_keywords:
- C2951
ms.assetid: c6f95aa2-c894-425b-a51c-d40d70c8daa1
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 4be1b3a298fc24572fcc44b9deb031c0d49b7332
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2951"></a>Ошибка компилятора C2951
объявления типов допускаются только в глобальной, пространство имен и области класса  
  
 Невозможно объявить универсальный класс или класс шаблона за пределами глобального или области видимости пространства имен. Если во включаемом файле объявлениях универсальный класс или шаблон, убедитесь, что файл включения находится в глобальной области видимости.  
  
 Следующий пример приводит к возникновению ошибки C2951:  
  
```  
// C2951.cpp  
template <class T>  
class A {};  
  
int main() {  
   template <class T>   // C2951  
   class B {};  
}  
```  
  
 C2951 также может возникнуть при использовании универсальных шаблонов:  
  
```  
// C2951b.cpp  
// compile with: /clr /c  
  
// OK  
generic <class T>   
ref class GC { };  
  
int main() {  
   generic <class T> ref class GC2 {};   // C2951  
}  
```
