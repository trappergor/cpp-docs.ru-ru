---
title: "Ошибка компилятора C3366 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3366
dev_langs:
- C++
helpviewer_keywords:
- C3366
ms.assetid: efc55bcf-c16d-43c1-a36f-87a6165fa2a8
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 930114bfb06019f13b4f44cc51b72922237a62f6
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3366"></a>Ошибка компилятора C3366
«переменная»: статические элементы данных управляемых или WinRTtypes должны быть определены внутри определения класса  
  
 Вы попытались сослаться на статический элемент класса WinRT, .NET или на интерфейс вне определения этого класса или интерфейса.  
  
 Компилятору требуется полное определение класса (для передачи метаданных после одного прохода), а статические элементы данных должны инициализироваться внутри класса.  
  
 Так, в следующем примере возникает ошибка C3366 и показано, как ее исправить.  
  
```  
// C3366.cpp  
// compile with: /clr /c  
ref class X {  
   public:  
   static int i;   // initialize i here to avoid C3366  
};  
  
int X::i = 5;      // C3366  
```  

