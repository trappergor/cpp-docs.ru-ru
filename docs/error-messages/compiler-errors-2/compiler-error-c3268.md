---
title: "C3268 Ошибка компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3268
dev_langs:
- C++
helpviewer_keywords:
- C3268
ms.assetid: d74a630c-daea-4e29-9759-83efef7fb184
caps.latest.revision: 5
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
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 13f7af86f70cb1d8539db593cbf0170a71f66498
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3268"></a>Ошибка компилятора C3268
"функция": универсальная функция или функция-член универсального класса не может иметь переменный список параметров  
  
 **/CLR: pure** и **/CLR: safe** параметры компилятора в Visual Studio 2015 являются устаревшими.  
  
 В разделе [универсальных типов](../../windows/generics-cpp-component-extensions.md) Дополнительные сведения.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C3268:  
  
```  
// C3268.cpp  
// compile with: /clr:pure /c  
generic <class ItemType>  
void Test(ItemType item, ...) {}   // C3268  
// try the following line instead  
// void Test(ItemType item) {}  
  
generic <class ItemType2>  
ref struct MyStruct { void Test(...){} };   // C3268  
// try the following line instead  
// ref struct MyStruct { void Test2(){} };   // OK  
```
