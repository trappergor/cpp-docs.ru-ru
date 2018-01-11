---
title: "Ошибка компилятора C2099 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2099
dev_langs: C++
helpviewer_keywords: C2099
ms.assetid: 30e151ee-d458-4901-b0c0-d45054a913f5
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 44e5faccc28877793aa42c5fb765e6d21eb19a1b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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