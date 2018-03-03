---
title: "Отсутствует тело функции или переменная | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
dev_langs:
- C++
helpviewer_keywords:
- function body
- variables, missing
ms.assetid: 1a88d809-b14f-46a4-97c4-3e48beb418f2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 356d0f0a71feccee953a0b1bd7dc54bc64a0e233
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="missing-function-body-or-variable"></a>Отсутствует тело функции или переменная
С прототипом функции компилятор может продолжать работу без ошибок, но компоновщик не может разрешить вызов адреса, поскольку код функции или переменная интервала зарезервированы. Эта ошибка не увидят до создания вызова функции, которую должен разрешить компоновщик.  
  
## <a name="example"></a>Пример  
 Вызов функции в основном вызовет ошибку LNK2019, поскольку прототипа позволяет компилятору считать, что функция существует.  Компоновщик обнаруживает, что это не так.  
  
```  
// LNK2019_MFBV.cpp  
// LNK2019 expected  
void DoSomething(void);  
int main() {  
   DoSomething();  
}  
```  
  
## <a name="example"></a>Пример  
 В C++ убедитесь, что включение реализации определенной функции для класса и не только для прототипа в определении класса. При определении класса за пределами файла заголовка, не забудьте включить имя класса перед функцией (`Classname::memberfunction`).  
  
```  
// LNK2019_MFBV_2.cpp  
// LNK2019 expected  
struct A {  
   static void Test();  
};  
  
// Should be void A::Test() {}  
void Test() {}  
  
int main() {  
   A AObject;  
   AObject.Test();  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Ошибка средств компоновщика LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)