---
title: Ошибка компилятора C3839 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3839
dev_langs:
- C++
helpviewer_keywords:
- C3839
ms.assetid: 0957faff-1e9f-439b-876b-85bd8d2c578d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cbb5541e07d168df36bae83f81b7b8a8a7273665
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33269518"
---
# <a name="compiler-error-c3839"></a>Ошибка компилятора C3839
нельзя изменять выравнивание в управляемом типе или типе WinRT  
  
 Выравнивание переменных в управляемых или типов среды выполнения Windows управляется средой CLR или среды выполнения Windows и не может быть изменено с [выравнивание](../../cpp/align-cpp.md).  
  
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