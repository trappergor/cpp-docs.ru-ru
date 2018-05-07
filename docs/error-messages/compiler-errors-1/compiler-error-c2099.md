---
title: Ошибка компилятора C2099 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2099
dev_langs:
- C++
helpviewer_keywords:
- C2099
ms.assetid: 30e151ee-d458-4901-b0c0-d45054a913f5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 28f525676f6d9238838f0dbc245d9771f99ebeb5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2099"></a>Ошибка компилятора C2099
инициализатор не является константой  
  
 Эта ошибка выдается только компилятором C и возникает только для неавтоматических переменных.  Компилятор инициализирует неавтоматические переменные при запуске программы, и значения, с которыми они инициализируются, должны быть константами.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C2099.  
  
```  
// C2099.c  
int j;  
int *p;  
j = *p;   // C2099 *p is not a constant  
```  
  
## <a name="example"></a>Пример  
 Ошибка C2099 может также возникать, если компилятор не может выполнить свертывание констант в **/fp:strict** , так как параметры среды, задающие точность вычислений с плавающей запятой (дополнительные сведения см. в разделе [_controlfp_s](../../c-runtime-library/reference/controlfp-s.md) ), могут отличаться во время компиляции и во время выполнения.  
  
 Когда происходит сбой свертывания констант, компилятор вызывает динамическую инициализацию, которая в С не разрешена.  
  
 Чтобы устранить эту ошибку, скомпилируйте модуль как CPP-файл или упростите выражение.  
  
 Для получения дополнительной информации см. [/fp (Specify Floating-Point Behavior)](../../build/reference/fp-specify-floating-point-behavior.md).  
  
 Следующий пример приводит к возникновению ошибки C2099.  
  
```  
// C2099_2.c  
// compile with: /fp:strict /c  
float X = 2.0 - 1.0;   // C2099  
float X2 = 1.0;   // OK  
```