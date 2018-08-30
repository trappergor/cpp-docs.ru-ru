---
title: Ошибка компилятора C3132 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3132
dev_langs:
- C++
helpviewer_keywords:
- C3132
ms.assetid: d54a3d12-336a-4ed0-ad4e-43cddac33b5e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bb32d65b119330e49773118e38e1c8b618d03cfc
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43204762"
---
# <a name="compiler-error-c3132"></a>Ошибка компилятора C3132
«параметр функции»: массивы параметров может применяться только к формальному аргументу с типом «одномерный управляемый массив»  
  
 [ParamArray](https://msdn.microsoft.com/library/system.paramarrayattribute.aspx) атрибут был применен к параметру, который не является одномерным массивом.  
  
 Следующий пример приводит к возникновению ошибки C3132:  
  
```  
// C3132.cpp  
// compile with: /clr /c  
using namespace System;  
void f( [ParamArray] Int32[,] );   // C3132  
void g( [ParamArray] Int32[] );   // C3132  
  
void h( [ParamArray] array<Char ^> ^ MyArray );   // OK  
  
```