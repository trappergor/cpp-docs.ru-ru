---
title: Ошибка компилятора C2951 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2951
dev_langs:
- C++
helpviewer_keywords:
- C2951
ms.assetid: c6f95aa2-c894-425b-a51c-d40d70c8daa1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0883b0942fdfbe3d55a540fbed35a0affc73be5b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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