---
title: "Предупреждение компилятора C4958 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4958
dev_langs:
- C++
helpviewer_keywords:
- C4958
ms.assetid: e79b9e9c-d572-4a3a-a3b6-60962b70864a
caps.latest.revision: 12
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 7deb92709adbb5a10148c092985e9a7c9f463c0c
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-c4958"></a>Предупреждение компилятора C4958
"операция": арифметика указателей недоступна для проверки  
  
 Использование арифметики указателей создает непроверяемый образ.  
  
 Дополнительные сведения см. в разделе [чистый и проверяемый код (C + +/ CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).  
  
 Это предупреждение выдается как ошибка и может быть отключено с [предупреждение](../../preprocessor/warning.md) pragma или [/wd](../../build/reference/compiler-option-warning-level.md) параметр компилятора.  
  
 В следующем примере возникает ошибка C4958:  
  
```  
// C4958.cpp  
// compile with: /clr:safe  
// #pragma warning( disable : 4958 )  
using namespace System;  
  
int main( ) {  
   Int32 arr[] = new Int32[10];  
   Int32* p = &arr[0];  
   p++;   // C4958  
}  
```  
  
 Компилятор реализует операции с массивами с использованием арифметики указателей. Таким образом, собственные массивы не подлежат проверке; используйте вместо них массив CLR. Дополнительные сведения см. в разделе [массива](../../windows/arrays-cpp-component-extensions.md).  
  
 В следующем примере возникает ошибка C4958:  
  
```  
// C4958b.cpp  
// compile with: /clr:safe  
// #pragma warning( disable : 4958 )  
  
int main() {  
   int array[5];  
   array[4] = 0;   // C4958  
}  
```
