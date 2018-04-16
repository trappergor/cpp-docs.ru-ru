---
title: Массив Param и многоточие | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- function overloading, argument matching
ms.assetid: 492e3f6c-1c4c-4e0c-a358-72f2d39c30be
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f6d256fd48d8c9f206619e6baa9a50a0278d30c3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="param-array-and-ellipsis"></a>Массив Param и многоточие
Приоритет массива param для разрешения перегруженных функций изменился с управляемых расширений для C++ к Visual C++.  
  
 В управляемых расширениях и новый синтаксис не поддерживается явное для массива param, C# и Visual Basic поддерживают. Вместо этого флагом обычный массив с атрибутом, как показано ниже:  
  
```  
void Trace1( String* format, [ParamArray]Object* args[] );  
void Trace2( String* format, Object* args[] );  
```  
  
 Поскольку массивы выглядят одинаково, `ParamArray` атрибут использует их для C# и других языков среды CLR как массив с изменяющимся числом элементов с каждым вызовом. Изменения в работе программы между управляемыми расширениями и нового синтаксиса заключается в разрешении набора перегруженных функций, в котором один экземпляр объявляет многоточие, а второй `ParamArray` атрибут, как в следующем примере, предоставляемые Приведенном Артуром Ларксбергом.  
  
```  
int fx(...); // 1  
int fx( [ParamArray] Int32[] ); // 2  
```  
  
 В управляемых расширениях многоточие имеет приоритет перед атрибут, который является разумным, поскольку атрибут не формальным аспектам языка. Однако в новом синтаксисе массив param теперь поддерживается непосредственно в рамках языка и он получает приоритет над кнопку с многоточием, так как оно является более строго типизированным. Таким образом в управляемых расширениях вызов  
  
```  
fx( 1, 2 );  
```  
  
 разрешает `fx(...)` в новом синтаксисе разрешения в `ParamArray` экземпляра. На off вероятность того, что поведение программы зависит от приоритета вызова экземпляра с многоточием над массивом `ParamArray`, будет необходимо изменить подпись или сбой вызова.  
  
## <a name="see-also"></a>См. также  
 [Общие изменения в языке (C++/CLI)](../dotnet/general-language-changes-cpp-cli.md)