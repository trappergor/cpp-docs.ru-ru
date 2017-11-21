---
title: "Ошибка компилятора C3891 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3891
dev_langs: C++
helpviewer_keywords: C3891
ms.assetid: 6e1a9458-97f5-4580-bc0f-aa97a1bfd20d
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b9db8f6142e4d2d99071d9d02255e0789a14dd50
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3891"></a>Ошибка компилятора C3891
«переменная»: данные-член литерала не может использоваться как l значение  
  
 Объект [литерала](../../windows/literal-cpp-component-extensions.md) переменной является константным выражением, и его значение нельзя изменить после инициализации в объявлении.  
  
 Следующий пример приводит к возникновению ошибки C3891:  
  
```  
// C3891.cpp  
// compile with: /clr  
ref struct Y1 {  
   literal int staticConst = 9;  
};  
  
int main() {  
   Y1::staticConst = 0;   // C3891  
}  
```