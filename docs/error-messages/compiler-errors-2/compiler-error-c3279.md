---
title: "Ошибка компилятора C3279 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3279
dev_langs:
- C++
helpviewer_keywords:
- C3279
ms.assetid: 639afc20-984c-4a95-be35-8bf9409f02d5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4535edc3ccca0c5abd972e31ee7284fad7384c31
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3279"></a>Ошибка компилятора C3279
Частичные и явные специализации, а также явные создания экземпляров шаблонов классов, объявленные в пространстве имен CLI, запрещены  
  
 Пространство имен `cli` определено Майкрософт и содержит псевдошаблоны. Компилятор Visual C++ не разрешает пользовательские, частичные и явные специализации, а также явное создание экземпляров шаблонов классов в этом пространстве имен.  
  
 При компиляции следующего примера возникнет ошибка C3279:  
  
```  
// C3279.cpp  
// compile with: /clr  
namespace cli {  
   template <> ref class array<int> {};   // C3279  
   template <typename T> ref class array<T, 2> {};   // C3279  
}  
```