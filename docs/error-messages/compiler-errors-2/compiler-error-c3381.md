---
title: Ошибка компилятора C3381 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3381
dev_langs:
- C++
helpviewer_keywords:
- C3381
ms.assetid: d276c89f-8377-4cb6-a8d4-7770885f06c4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a27961694bc5fad4080d8aceaf2f1cb65404319c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3381"></a>Ошибка компилятора C3381
«сборка»: спецификаторы доступа к сборке доступны только в коде, скомпилированном с параметром/CLR  
  
 Собственные типы могут быть видны вне сборки, но можно указать только доступ к сборке для собственных типов в **/CLR** компиляции.  
  
 Дополнительные сведения см. в разделе [введите видимость](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) и [/CLR (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C3381.  
  
```  
// C3381.cpp  
// compile with: /c  
public class A {};   // C3381  
```