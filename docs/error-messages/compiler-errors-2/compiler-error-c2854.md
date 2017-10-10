---
title: "Ошибка компилятора C2854 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2854
dev_langs:
- C++
helpviewer_keywords:
- C2854
ms.assetid: 917fec9c-790a-4149-8dfc-00d17a09199c
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 0f8423af7be34d431ab8ace8ca512d857611c6c3
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2854"></a>Ошибка компилятора C2854
Синтаксическая ошибка в #pragma hdrstop  
  
 `#pragma hdrstop` Указано недопустимое имя файла. Директива pragma может следовать необязательное имя файла в круглые скобки и кавычки:  
  
 Следующий пример приводит к возникновению ошибки C2854:  
  
```  
// C2854.cpp  
// compile with: /c  
#pragma hdrstop( "\\source\\pchfiles\\myheader.pch" ]   // C2854  
// try the following line instead  
// #pragma hdrstop( "\\source\\pchfiles\\myheader.pch" )  
```
