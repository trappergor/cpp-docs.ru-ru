---
title: "Ошибка компилятора C2755 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2755
dev_langs: C++
helpviewer_keywords: C2755
ms.assetid: 8ee4eeb6-4757-4efe-9100-38ff4a96f1de
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b99ce492806b46231293ca433d24db1b153fb982
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2755"></a>Ошибка компилятора C2755
«параметр»: параметр частичной специализации не являющийся типом должен быть простым идентификатором  
  
 Параметр не является типом должен быть простым идентификатором, то, что компилятор может разрешить во время компиляции один идентификатор или значение константы.  
  
 Следующий пример приводит к возникновению ошибки C2755:  
  
```  
// C2755.cpp  
template<int I, int J>  
struct A {};  
  
template<int I>   
struct A<I,I*5> {};   // C2755  
// try the following line instead  
// struct A<I,5> {};  
```