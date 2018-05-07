---
title: Ошибка компилятора C3846 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3846
dev_langs:
- C++
helpviewer_keywords:
- C3846
ms.assetid: c470f8a5-106b-4efb-b8dc-e1319e04130f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 97d5650d1743ba379ce065d4051bfed807a1df71
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3846"></a>Ошибка компилятора C3846
«символ»: не удается импортировать символ из «сборки 2»: «символ» уже был импортирован из другой сборки «сборка1»  
  
 Не удалось импортировать символ из указанной сборки, поскольку он ранее был импортирован из указанной сборки.  
  
## <a name="example"></a>Пример
Следующий пример приводит к возникновению ошибки C3846:  
  
```  
// C3846a.cpp  
// compile with: /LD /clr  
public ref struct G  
{  
};  
```  
  
 И затем Скомпилируйте следующий:  
  
```  
// C3846b.cpp  
// compile with: /clr  
#using "c3846a.dll"  
#using "c3846a.obj"   // C3846  
  
int main()  
{  
}  
```  
