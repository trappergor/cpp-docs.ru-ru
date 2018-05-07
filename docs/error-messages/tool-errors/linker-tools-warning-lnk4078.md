---
title: Предупреждение средств компоновщика LNK4078 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4078
dev_langs:
- C++
helpviewer_keywords:
- LNK4078
ms.assetid: 5a16796d-6caf-42d9-8f65-b042843eafb8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 252e2e7bdd011b289dbb3ec6164444bbe0bc7b44
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-warning-lnk4078"></a>Предупреждение средств компоновщика LNK4078
» Имя раздела «найдено несколько разделов с разными атрибутами  
  
 LINK обнаружил два или дополнительные разделы, которые имеют одинаковое имя, но с разными атрибутами.  
  
 Это предупреждение может быть вызвано файла импорта библиотеки или экспорта, была создана в предыдущей версии LINK или LIB.  
  
 Повторно создайте файл и повторно выполнить компоновку.  
  
## <a name="example"></a>Пример  
 LNK4078 также может быть вызвано это критическое изменение: раздел с именем [init_seg](../../preprocessor/init-seg.md) на x86 чтения и записи, доступной теперь только для чтения.  
  
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