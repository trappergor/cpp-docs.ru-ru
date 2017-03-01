---
title: "Ошибка компилятора C3839 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3839
dev_langs:
- C++
helpviewer_keywords:
- C3839
ms.assetid: 0957faff-1e9f-439b-876b-85bd8d2c578d
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: ce476fe84c4c998c1775cb9b492aaba5dae68da5
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3839"></a>Ошибка компилятора C3839
нельзя изменять выравнивание в управляемом типе или типе WinRT  
  
 Выравнивание переменных в управляемых или типов среды выполнения Windows управляет среда CLR или среды выполнения Windows и не может быть изменен с [выравнивания](../../cpp/align-cpp.md).  
  
 Следующий пример приводит к возникновению ошибки C3839:  
  
```  
// C3839a.cpp  
// compile with: /clr  
ref class C  
{  
public:  
   __declspec(align(32)) int m_j; // C3839  
};  
  
int main()  
{  
}  
```
