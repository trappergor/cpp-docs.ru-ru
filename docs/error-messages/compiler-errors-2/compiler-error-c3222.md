---
title: "Ошибка компилятора C3222 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3222
dev_langs: C++
helpviewer_keywords: C3222
ms.assetid: 5624bde8-2fd0-4b8b-92ce-5dfbaf91cf93
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0028b9540127433bdbd17b01f1a5a3dfd9361558
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3222"></a>Ошибка компилятора C3222
"parameter": нельзя объявить аргументы по умолчанию для функций-членов управляемого типа, типа WinRT или универсальных функций  
  
Запрещено объявлять параметр метода с аргументом по умолчанию. Перегруженные формы метода — один из способов решения этой проблемы. То есть вам нужно определить метод с тем же именем без параметров и затем инициализировать переменную в теле метода.  
  
Следующий пример приводит к возникновению ошибки C3222:  
  
```  
// C3222_2.cpp  
// compile with: /clr  
public ref class G {  
   void f( int n = 0 );   // C3222  
};  
```  
