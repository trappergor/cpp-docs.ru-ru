---
title: "Ошибка компилятора C3385 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3385
dev_langs: C++
helpviewer_keywords: C3385
ms.assetid: 5f1838c1-986e-47db-8dbc-e06976b83cf3
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9f92dd2ade185ddc90f1c5e057c4076e7859f298
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3385"></a>Ошибка компилятора C3385
"класс::функция": функция с пользовательским аргументом DllImport не может возвращать экземпляр класса  
  
 Функция, определенная как находящаяся в DLL-файле, указанная с атрибутом `DllImport` , не может возвращать экземпляр класса.  
  
 В следующем примере возникает ошибка C3385:  
  
```  
// C3385.cpp  
// compile with: /clr /c  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
struct SomeStruct1 {};  
  
public ref struct Wrap {  
   [ DllImport("somedll.dll", CharSet=CharSet::Unicode) ]  
   static SomeStruct1 f1([In, Out] SomeStruct1 *pS);   // C3385  
};  
```  
