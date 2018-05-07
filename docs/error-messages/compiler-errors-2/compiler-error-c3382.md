---
title: Ошибка компилятора C3382 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3382
dev_langs:
- C++
helpviewer_keywords:
- C3382
ms.assetid: a7603abd-ac4e-4ae6-a02b-3bdc6d1908a6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f8bcca58aecc3d5a5e7b621f45e102690c9f138c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3382"></a>Ошибка компилятора C3382
sizeof при использовании параметра /clr:safe не поддерживается  
  
 При выполнении компиляции с параметром **/clr:safe** выходной файл является проверяемым строго типизированным файлом, и параметр sizeof не поддерживается, так как он возвращает значение типа size_t, размер которого зависит от операционной системы.  
  
 Дополнительные сведения см. в следующих разделах:  
  
-   [Оператор sizeof](../../cpp/sizeof-operator.md)  
  
-   [/clr (компиляция среды выполнения)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [Общие вопросы использования Visual C++ для 64-разрядных систем](../../build/common-visual-cpp-64-bit-migration-issues.md)  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C3382:  
  
```  
// C3382.cpp  
// compile with: /clr:safe  
int main() {  
   sizeof( char );   // C3382  
}  
```