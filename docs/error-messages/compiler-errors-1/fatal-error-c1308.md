---
title: "Неустранимая ошибка C1308 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1308
dev_langs:
- C++
helpviewer_keywords:
- C1308
ms.assetid: 46177997-069e-433a-8e20-93c846d78ffd
caps.latest.revision: 11
author: corob-msft
ms.author: corob
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 4d2481a724ac98d325dd2bd05714d410f5e75e3c
ms.lasthandoff: 02/24/2017

---
# <a name="fatal-error-c1308"></a>Неустранимая ошибка C1308
компоновка сборок не поддерживается  
  
 NETMODULE поддерживается как входной модуль компоновщика, но не сборка. Это ошибка может возникать при попытке связать сборки, скомпилированной с параметром `/clr:safe`.  
  
 Дополнительные сведения см. в разделе [NETMODULE-файлы в качестве входных данных компоновщика](../../build/reference/netmodule-files-as-linker-input.md).  
  
 Следующий пример приводит к возникновению ошибки C1308:  
  
```  
// C1308.cpp  
// compile with: /clr:safe /LD  
public ref class MyClass {  
public:  
   int i;  
};  
```  
  
 И потом  
  
```  
// C1308b.cpp  
// compile with: /clr /link C1308b.obj C1308.dll  
// C1308 expected  
#using "C1308.dll"  
int main() {  
   MyClass ^ my = gcnew MyClass();  
}  
```
