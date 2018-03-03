---
title: "Ошибка компилятора C3386 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3386
dev_langs:
- C++
helpviewer_keywords:
- C3386
ms.assetid: 93fa8c33-0f10-402b-8eec-b0a217a1f8dc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0c0b0ed0bf17d568ebba3c8e5fdff2e02b5eae6b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3386"></a>Ошибка компилятора C3386
«Тип»: __declspec(dllexport) /\__declspec(dllimport) не может применяться к управляемого типа или WinRTtype  
  
 `dllimport` И [dllexport](../../cpp/dllexport-dllimport.md) `__declspec` модификаторы недопустимы для управляемого типа или среды выполнения Windows тип.  
  
 В следующем примере показано возникновение ошибки C3386 и приводятся сведения по ее устранению.  
  
```  
// C3386.cpp  
// compile with: /clr /c  
ref class __declspec(dllimport) X1 {   // C3386  
// try the following line instead  
// ref class X1 {  
};  
```