---
title: Предупреждение (уровень 4) C4266 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4266
dev_langs:
- C++
helpviewer_keywords:
- C4266
ms.assetid: 90ec5f5b-3451-4c16-bb1b-c30a626bdaa0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ecbf7326b79cd22cdff6c094d8dc0c7f9113deb6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4266"></a>Предупреждение компилятора (уровень 4) C4266
«функция»: нет доступного переопределения для виртуальной функции-члена из базового типа «тип»; функция скрыта  
  
 Производный класс не переопределяет все перегрузки виртуальной функции.  
  
 Это предупреждение отключено по умолчанию.  Подробнее: [Выключенные по умолчанию предупреждения компилятора](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .  
  
 Следующий пример приводит к возникновению ошибки C4266:  
  
```  
// C4266.cpp  
// compile with: /W4 /c  
#pragma warning (default : 4266)  
class Engine {  
public:  
   virtual void OnException(int&,int);  
   virtual void OnException(int&,int&,int);  
};  
  
class LocalBinding : private Engine {  
   virtual void OnException(int&,int);  
};   // C4266  
```  
  
 Возможное решение  
  
```  
// C4266b.cpp  
// compile with: /W4 /c  
#pragma warning (default : 4266)  
class Engine {  
public:  
   virtual void OnException(int&,int);  
   virtual void OnException(int&,int&,int);  
};  
  
class LocalBinding : private Engine {  
   virtual void OnException(int&,int);  
   virtual void OnException(int&, int&, int);  
};  
```