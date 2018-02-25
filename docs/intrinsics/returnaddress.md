---
title: "_ReturnAddress | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- _ReturnAddress
dev_langs:
- C++
helpviewer_keywords:
- _ReturnAddress intrinsic
- ReturnAddress intrinsic
ms.assetid: 7f4a5811-35e6-4f64-ba7c-21203380eeda
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ae1437d6523b94071a5e7655bfa2e7094d89305a
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="returnaddress"></a>_ReturnAddress
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft  
 `_ReturnAddress` Предоставляет адрес инструкции в вызывающей функции, которая будет выполняться после возврата управления в вызывающий объект.  
  
 Построение следующие программы и в пошаговом режиме в отладчике. При пошаговом выполнении программы Обратите внимание на адрес, который возвращается из `_ReturnAddress`. Затем, сразу после возврата из функции где `_ReturnAddress` используется, и откройте [как: использование окна дизассемблирования](/visualstudio/debugger/how-to-use-the-disassembly-window) и обратите внимание, что адрес следующую инструкцию для выполнения отвечает адрес, возвращенный из `_ReturnAddress`.  
  
 Оптимизацию, например встраивание может повлиять на обратный адрес. Например, если ниже примера программы компилируется с [/Ob1](../build/reference/ob-inline-function-expansion.md), `inline_func` будет подставляться в вызывающей функции `main`. Таким образом, вызовы `_ReturnAddress` из `inline_func` и `main` будет каждая из которых создает то же значение.  
  
 Когда `_ReturnAddress` используется в программе, которая скомпилирована с [/CLR](../build/reference/clr-common-language-runtime-compilation.md), функция, содержащая `_ReturnAddress` вызов будет компилироваться как собственную функцию. Когда функция скомпилирована как управляемые вызовы в функцию, содержащую `_ReturnAddress`, `_ReturnAddress` может вести себя неожиданным образом.  
  
## <a name="requirements"></a>Требования  
 **Файл заголовка** \<intrin.h >  
  
## <a name="example"></a>Пример  
  
```  
// compiler_intrinsics__ReturnAddress.cpp  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(_ReturnAddress)  
  
__declspec(noinline)  
void noinline_func(void)  
{  
   printf("Return address from %s: %p\n", __FUNCTION__, _ReturnAddress());  
}  
  
__forceinline  
void inline_func(void)  
{  
   printf("Return address from %s: %p\n", __FUNCTION__, _ReturnAddress());  
}  
  
int main(void)  
{  
   noinline_func();   
   inline_func();  
   printf("Return address from %s: %p\n", __FUNCTION__, _ReturnAddress());  
  
   return 0;  
}  
```  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [_AddressOfReturnAddress](../intrinsics/addressofreturnaddress.md)   
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)