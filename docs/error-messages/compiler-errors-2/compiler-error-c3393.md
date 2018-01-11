---
title: "Ошибка компилятора C3393 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3393
dev_langs: C++
helpviewer_keywords: C3393
ms.assetid: d57f7c69-0a02-4fe3-9e45-bc62644fd77c
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d0793d7272f5fe31d45c78ce662a477526fe26da
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3393"></a>Ошибка компилятора C3393
синтаксическая ошибка в предложении ограничения: "идентификатор" не является типом  
  
 Идентификатор, переданный в ограничение, которое должно быть типом, не является типом.  Дополнительные сведения см. в разделе [ограничений для параметров универсального типа (C + +/ CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md).  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C3393:  
  
```  
// C3393.cpp  
// compile with: /clr /c  
void MyInterface() {}  
interface class MyInterface2 {};  
  
generic<typename T>  
where T : MyInterface   // C3393  
// try the following line instead  
// where T : MyInterface2  
ref class R {};  
```