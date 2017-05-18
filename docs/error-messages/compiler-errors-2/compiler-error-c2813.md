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
caps.latest.revision: 9
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
ms.openlocfilehash: fc5f5437751abf6bcb11299e8484a199275db970
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2813"></a>Ошибка компилятора C2813
\#Импорт не поддерживается с параметром /MP  
  
 C2813 выводится в случае если в команде компилятора указать **/MP** параметр компилятора и два или более файлов для компиляции и один или несколько файлов содержит[#import](../../preprocessor/hash-import-directive-cpp.md) директивы препроцессора. [#Import](../../preprocessor/hash-import-directive-cpp.md) директивы создает классы C++ из типов в указанной библиотеки типов и затем записывает эти классы в два файла заголовка. [#Import](../../preprocessor/hash-import-directive-cpp.md) директива не поддерживается, поскольку если несколько блоков компиляции импортируют той же библиотеки типов, между блоками возникает конфликт при попытке записать файл заголовка, в то же время.  
  
 Эта ошибка компилятора и **/MP** были добавлены в параметр компилятора [!INCLUDE[vs_orcas_long](../../atl/reference/includes/vs_orcas_long_md.md)].  
  
## <a name="example"></a>Пример  
 Приведенный ниже пример приводит к возникновению ошибки C2813. Командная строка в комментарии "compile with:" предписывает компилятору использовать параметры компилятора **/MP** и **/c** для компиляции нескольких файлов. Содержит по крайней мере один из файлов [#import](../../preprocessor/hash-import-directive-cpp.md) директивы. Один и тот же файл используется дважды для проверки данного примера.  
  
```  
// C2813.cpp  
// compile with: /MP /c C2813.cpp C2813.cpp  
#import "C:\windows\system32\stdole2.tlb"   // C2813  
int main()   
{  
}  
```
