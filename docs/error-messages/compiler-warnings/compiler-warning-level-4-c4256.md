---
title: "Предупреждение (уровень 4) C4256 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4256
dev_langs: C++
helpviewer_keywords: C4256
ms.assetid: a755a32e-895a-4837-a2b5-4ea06b736798
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4bbaec27948f061cb21eeb432446517d4f9a6b2c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4256"></a>Предупреждение компилятора (уровень 4) C4256
«функция»: конструктор класса с виртуальными базами содержит «...»; вызовы могут оказаться несовместимыми с более ранними версиями Visual C++  
  
 Возможные несовместимости.  
  
 Рассмотрим следующий пример кода: Если определение конструктора S2::S2 (int i,...) был скомпилирован с использованием версии компилятора Visual C++ до версии 7, но следующий пример компилируется с помощью текущей версии, вызов конструктора для S3 будет работать неправильно из-за Изменение соглашения о вызовах особых случаев. Если оба были скомпилированы с помощью Visual C++ 6.0, вызов не будет работать правильно, если только не переданы параметры для многоточия.  
  
 Чтобы устранить это предупреждение  
  
1.  Не используйте кнопку с многоточием в конструкторе.  
  
2.  Убедитесь, что все компоненты в проекте построены с использованием текущей версии (включая все библиотеки, которые могут определять или ссылаться на данный класс), после чего отключите предупреждение с помощью [предупреждение](../../preprocessor/warning.md) pragma.  
  
 Следующий пример приводит к возникновению ошибки C4256:  
  
```  
// C4256.cpp  
// compile with: /W4  
// #pragma warning(disable : 4256)  
struct S1  
{  
};  
  
struct S2: virtual public S1  
{  
   S2( int i, ... )    // C4256  
   {  
      i = 0;  
   }  
   /*  
   // try the following line instead  
   S2( int i)  
   {  
      i = 0;  
   }  
   */  
};  
  
void func1()  
{  
   S2 S3( 2, 1, 2 );   // C4256  
   // try the following line instead  
   // S2 S3( 2 );  
}  
  
int main()  
{  
}  
```