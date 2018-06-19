---
title: Ошибка компилятора C3366 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3366
dev_langs:
- C++
helpviewer_keywords:
- C3366
ms.assetid: efc55bcf-c16d-43c1-a36f-87a6165fa2a8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c26bfbb5d66ad22484184bd361f14004ed8aa30c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33254278"
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
