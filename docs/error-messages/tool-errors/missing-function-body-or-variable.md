---
title: Отсутствует тело функции или переменная | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
dev_langs:
- C++
helpviewer_keywords:
- function body
- variables, missing
ms.assetid: 1a88d809-b14f-46a4-97c4-3e48beb418f2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 54e2b8c5831eb6d487cf530df1b733b73580cbb8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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