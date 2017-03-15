---
title: "Предупреждение (уровень 3) C4398 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4398
dev_langs:
- C++
helpviewer_keywords:
- C4398
ms.assetid: b6221432-9fed-4272-a547-a73f587904e6
caps.latest.revision: 6
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
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 18270bb89bcc5d1855750c572a5b6fb9e51c2ba3
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-3-c4398"></a>Предупреждение компилятора (уровень 3) C4398
«переменная»: глобальный объект для каждого процесса может работать неправильно с несколькими доменами приложений; следует использовать __declspec(appdomain)  
  
 Виртуальная функция с [__clrcall](../../cpp/clrcall.md) соглашение о вызовах в машинный тип вызывает создание каждого vtable домена приложения. Такой переменной могут некорректно при использовании в нескольких доменах приложений.  
  
 Можно устранить это предупреждение, явно пометив переменной `__declspec(appdomain)`. В версиях Visual Studio до 2017 г. Visual Studio, можно устранить это предупреждение, скомпилировав с **/CLR: pure**, который создает глобальные переменные для каждого домена приложения по умолчанию.  
  
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
