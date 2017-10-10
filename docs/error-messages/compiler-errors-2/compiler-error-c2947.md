---
title: "Ошибка компилятора C2947 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2947
dev_langs:
- C++
helpviewer_keywords:
- C2947
ms.assetid: 6c056f62-ec90-4883-8a67-aeeb6ec13546
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: bb5b22d4fd4b874e19cff564dec96609f9da0789
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2947"></a>Ошибка компилятора C2947
ожидается ">" для завершения конструкции, обнаружен «синтаксис»  
  
 Список аргументов универсальный класс или шаблон может не были завершены правильно.  
  
 C2947 также может возникать вследствие ошибок синтаксиса.  
  
 Следующий пример приводит к возникновению ошибки C2947:  
  
```  
// C2947.cpp  
// compile with: /c  
template <typename T>=   // C2947  
// try the following line instead  
// template <typename T>  
struct A {};  
```
