---
title: 'Как: проверка на равенство (C + +/ CLI) | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- equality, testing for
ms.assetid: 9115e298-9f75-452d-bdfb-6eeb0fa0b3c6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0c32bd9c73b7251f311593b547d4f3abdd33d7c5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-test-for-equality-ccli"></a>Практическое руководство. Проверка на равенство (C++/CLI)
В следующем примере проверка на равенство, использующий управляемые расширения для C++ основана на которые указывают дескрипторы.  
  
## <a name="example"></a>Пример  
  
```  
// mcppv2_equality_test.cpp  
// compile with: /clr /LD  
using namespace System;  
  
bool Test1() {  
   String ^ str1 = "test";  
   String ^ str2 = "test";  
   return (str1 == str2);  
}  
```  
  
 IL-код для этой программы показывает, что возвращаемое значение реализуется с помощью вызова функции op_Equality.  
  
```  
IL_0012:  call       bool [mscorlib]System.String::op_Equality(string,  
                                                               string)  
```  
  
## <a name="see-also"></a>См. также  
 [Управляемые типы (C++/CLI)](../dotnet/managed-types-cpp-cli.md)