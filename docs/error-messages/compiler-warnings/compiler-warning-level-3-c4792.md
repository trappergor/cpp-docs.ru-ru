---
title: Ошибка компилятора предупреждение (уровень 3) C4792 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4792
dev_langs:
- C++
helpviewer_keywords:
- C4792
ms.assetid: c047ce69-a622-44e1-9425-d41aa9261c61
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a4b0867305c56fc551e55680b6ed48bdb701cc09
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-3-c4792"></a>Предупреждение компилятора (уровень 3) C4792
на функцию "функция", объявленную с использованием sysimport, ссылается машинный код; импортируйте библиотеку, необходимую для компоновки  
  
 Собственная функция, импортированная в программу с помощью DllImport, вызывается из неуправляемой функции. Таким образом, необходимо привязать библиотеку импорта для библиотеки DLL.  
  
 Это предупреждение нельзя разрешить в коде или путем изменения способа компиляции. Используйте прагму [warning](../../preprocessor/warning.md) , чтобы отключить это предупреждение.  
  
 В следующем примере возникает ошибка C4792:  
  
```  
// C4792.cpp  
// compile with: /clr /W3  
// C4792 expected  
using namespace System::Runtime::InteropServices;  
[DllImport("msvcrt")]  
extern "C" int __cdecl puts(const char *);  
int main() {}  
  
// Uncomment the following line to resolve.  
// #pragma warning(disable : 4792)  
#pragma unmanaged  
void func(void){  
   puts("test");  
}  
```