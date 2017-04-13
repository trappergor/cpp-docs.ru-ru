---
title: "Ошибка компилятора C3279 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3279
dev_langs:
- C++
helpviewer_keywords:
- C3279
ms.assetid: 639afc20-984c-4a95-be35-8bf9409f02d5
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: cd0e6c10a544cf9b23edd93a4268122135adb6af
ms.lasthandoff: 04/12/2017

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
