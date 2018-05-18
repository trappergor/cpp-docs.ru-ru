---
title: Предупреждение (уровень 1) C4812 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4812
dev_langs:
- C++
helpviewer_keywords:
- C4812
ms.assetid: a7f5721f-2019-44de-ad62-ed30bac8b1f3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 05ff26f9adf9548553cd76033bba3aa9cefe9417
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4812"></a>Предупреждение компилятора (уровень 1) C4812
устаревший стиль объявления: используйте "новый_синтаксис" как альтернативу  
  
 В текущей версии Visual C++ явная специализация конструкторов все еще поддерживается, однако в следующей версии эта поддержка может отсутствовать.  
  
 Следующий пример приводит к возникновению предупреждения C4812:  
  
```  
// C4812.cpp  
// compile with: /W1 /c  
template <class T>   
class MyClass;  
  
template<class T>  
class MyClass<T*> {  
   MyClass();  
};  
  
template<class T>  
MyClass<T*>::MyClass<T*>() {}   // C4812  
// try the following line instead  
// MyClass<T*>::MyClass() {}  
```