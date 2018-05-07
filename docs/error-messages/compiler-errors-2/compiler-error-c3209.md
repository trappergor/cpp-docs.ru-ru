---
title: Ошибка компилятора C3209 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3209
dev_langs:
- C++
helpviewer_keywords:
- C3209
ms.assetid: 1de44e39-69d1-4894-8f89-ff92136e8e5d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9723d444fb90ea4a8bbaac89f5fffd923ea75a76
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3209"></a>Ошибка компилятора C3209
«класс»: универсальный класс должен быть управляемого типа или WinRTclass  
  
 Универсальный класс должен быть управляемым классом или классом среды выполнения Windows.  
  
 В следующем примере показано возникновение ошибки C3209 и приводятся сведения по ее устранению.  
  
```  
// C3209.cpp  
// compile with: /clr  
generic <class T>  
class C {};   // C3209  
  
// OK - ref class can be generic  
generic <class T>  
ref class D {};  
```