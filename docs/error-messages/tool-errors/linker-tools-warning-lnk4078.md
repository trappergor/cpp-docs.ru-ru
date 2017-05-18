---
title: "Предупреждение средств компоновщика LNK4078 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4078
dev_langs:
- C++
helpviewer_keywords:
- LNK4078
ms.assetid: 5a16796d-6caf-42d9-8f65-b042843eafb8
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 81f5c9e42d05bbc5646ad0b3fd27fd39408301b1
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-warning-lnk4078"></a>Предупреждение средств компоновщика LNK4078
несколько разделы» имя раздела «с разными атрибутами  
  
 LINK обнаружил два или дополнительные разделы, имеющие одинаковое имя, но с разными атрибутами.  
  
 Это предупреждение может быть вызвано файла импорта библиотеки или экспорта, была создана в предыдущей версии LINK или LIB.  
  
 Повторно создайте файл и повторно скомпоновать.  
  
## <a name="example"></a>Пример  
 LNK4078 также может быть вызвано критических изменений: раздел с именем, [init_seg](../../preprocessor/init-seg.md) на x86 чтения и записи, он имеет теперь только для чтения.  
  
 Следующий пример приводит к возникновению ошибки LNK4078.  
  
```  
// LNK4078.cpp  
// compile with: /W1  
// LNK4078 expected  
#include <stdio.h>  
#pragma warning(disable : 4075)  
typedef void (__cdecl *PF)(void);  
int cxpf = 0;   // number of destructors to call  
PF pfx[200];   // pointers to destructors.  
  
struct A { A() {} };  
  
int myexit (PF pf) { return 0; }  
  
#pragma section(".mine$a", read, write)  
// try the following line instead  
// #pragma section(".mine$a", read)  
__declspec(allocate(".mine$a")) int ii = 1;  
  
#pragma section(".mine$z", read, write)  
// try the following line instead  
// #pragma section(".mine$z", read)  
__declspec(allocate(".mine$z")) int i = 1;  
  
#pragma data_seg()  
#pragma init_seg(".mine$m", myexit)  
A bbbb;   
A cccc;  
int main() {}  
```
