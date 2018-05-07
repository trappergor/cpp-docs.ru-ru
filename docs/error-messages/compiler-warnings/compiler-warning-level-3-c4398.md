---
title: Предупреждение (уровень 3) C4398 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4398
dev_langs:
- C++
helpviewer_keywords:
- C4398
ms.assetid: b6221432-9fed-4272-a547-a73f587904e6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8ace2df75b5d2579b66a4d3930470021726ba4c9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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