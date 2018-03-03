---
title: "Ошибка компилятора C2813 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- C2813
ms.assetid: 6cf2135f-7b82-42d1-909a-5e864308a09c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3cc6ac0e287894dc2202814c55dac37569650f5e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2813"></a>Ошибка компилятора C2813
\#Импорт не поддерживается с параметром /MP  
  
 Ошибка C2813 выводится в случае, когда в команде компилятора задается параметр компилятора **/MP** , а также два или более файлов для компиляции, и при этом один или несколько файлов содержат директиву препроцессора[#import](../../preprocessor/hash-import-directive-cpp.md) . Директива [#import](../../preprocessor/hash-import-directive-cpp.md) создает классы C++ на основе типов в указанной библиотеке типов, а затем записывает эти классы в два файла заголовков. Директива [#import](../../preprocessor/hash-import-directive-cpp.md) не поддерживается, так как в случае, если несколько блоков компиляции импортируют одну и ту же библиотеку типов, между блоками возникает конфликт при попытке одновременной записи одних и тех же файлов заголовков.  
  
 Эта ошибка компилятора и **/MP** параметр компилятора впервые появились в Visual Studio 2008.  
  
## <a name="example"></a>Пример  
 Приведенный ниже пример приводит к возникновению ошибки C2813. Командная строка в комментарии "compile with:" предписывает компилятору использовать параметры компилятора **/MP** и **/c** для компиляции нескольких файлов. По крайней мере один из файлов содержит директиву [#import](../../preprocessor/hash-import-directive-cpp.md) . Один и тот же файл используется дважды для проверки данного примера.  
  
```  
// C2813.cpp  
// compile with: /MP /c C2813.cpp C2813.cpp  
#import "C:\windows\system32\stdole2.tlb"   // C2813  
int main()   
{  
}  
```