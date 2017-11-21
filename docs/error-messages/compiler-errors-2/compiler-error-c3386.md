---
title: "Ошибка компилятора C3386 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3386
dev_langs: C++
helpviewer_keywords: C3386
ms.assetid: 93fa8c33-0f10-402b-8eec-b0a217a1f8dc
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8b912d1d75ae120f993c3641ff2e2b561910b4aa
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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