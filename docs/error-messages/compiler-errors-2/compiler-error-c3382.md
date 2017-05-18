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
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 2cb6ac6aa2409defea2d31591b348b2f2aae403b
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

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
