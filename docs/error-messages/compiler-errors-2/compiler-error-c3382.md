---
title: "Ошибка компилятора C3382 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3382
dev_langs:
- C++
helpviewer_keywords:
- C3382
ms.assetid: a7603abd-ac4e-4ae6-a02b-3bdc6d1908a6
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c58047e409c60fd2b6cb65418131f6aadb1430a2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3382"></a>Ошибка компилятора C3382
sizeof при использовании параметра /clr:safe не поддерживается  
  
 При выполнении компиляции с параметром **/clr:safe** выходной файл является проверяемым строго типизированным файлом, и параметр sizeof не поддерживается, так как он возвращает значение типа size_t, размер которого зависит от операционной системы.  
  
 Дополнительные сведения см. в следующих разделах:  
  
-   [Оператор sizeof](../../cpp/sizeof-operator.md)  
  
-   [/ CLR (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
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