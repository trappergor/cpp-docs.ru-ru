---
title: Ошибка компилятора C2728 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2728
dev_langs:
- C++
helpviewer_keywords:
- C2728
ms.assetid: 65635f91-1cd1-46e4-9ad7-14726d0546af
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e954ba38efc2e1ef7bc4b203c8b54876f7aae0ed
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33234460"
---
# <a name="compiler-error-c2728"></a>Ошибка компилятора C2728
type: собственный массив не может содержать этот тип  
  
 Синтаксис для создания массива использовался для создания массива или управляемых объектов или объектов WinRT. Невозможно создать массив управляемых объектов или объектов WinRT, используя синтаксис управляемого массива.  
  
 Дополнительные сведения см. в описании [array](../../windows/arrays-cpp-component-extensions.md).  
  
 В следующем примере показано возникновение ошибки C2728 и приводятся сведения по ее устранению.  
  
```  
// C2728.cpp  
// compile with: /clr  
  
int main() {  
   int^ arr[5];   // C2728  
  
   // try the following line instead  
   array<int>^arr2;  
}  
```  
