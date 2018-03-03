---
title: "Предупреждение (уровень 3) C4398 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4398
dev_langs:
- C++
helpviewer_keywords:
- C4398
ms.assetid: b6221432-9fed-4272-a547-a73f587904e6
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d5ce6355e50c1ea2594820388edc34c69ea0e899
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4398"></a>Предупреждение компилятора (уровень 3) C4398
«переменная»: глобальный объект для каждого процесса может работать неправильно с несколькими доменами приложений; Рассмотрите возможность использования __declspec(appdomain)  
  
 Виртуальная функция с [__clrcall](../../cpp/clrcall.md) соглашение о вызовах в машинный тип вызывает создание в vtable домена приложения. Такой переменной могут некорректно при использовании в нескольких доменах приложений.  
  
 Чтобы устранить это предупреждение явным созданием переменной `__declspec(appdomain)`. В версиях Visual Studio до Visual Studio 2017 г., чтобы устранить это предупреждение при компиляции с **/CLR: pure**, что делает глобальные переменные для каждого домена приложения по умолчанию.  
  
 Дополнительные сведения см. в разделе [appdomain](../../cpp/appdomain.md) и [домены приложений и Visual C++](../../dotnet/application-domains-and-visual-cpp.md).  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4398.  
  
```  
// C4398.cpp  
// compile with: /clr /W3 /c  
struct S {  
   virtual void f( System::String ^ );   // String^ parameter makes function __clrcall  
};  
  
S glob_s;   // C4398  
__declspec(appdomain) S glob_s2;   // OK  
```