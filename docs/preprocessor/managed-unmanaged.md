---
title: "управляемые, неуправляемые | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc-pragma.unmanaged
- managed_CPP
- unmanaged_CPP
- vc-pragma.managed
dev_langs:
- C++
helpviewer_keywords:
- managed pragma
- pragmas, unmanaged
- pragmas, managed
- unmanaged pragma
ms.assetid: f072ddcc-e1ec-408a-8ce1-326ddb60e4a4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bc7e86e053cec68a3a25c753b7c3b7fb8ab50363
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="managed-unmanaged"></a>managed, unmanaged
Позволяет на уровне функций контролировать режим их компиляции: с управляемым или неуправляемым кодом.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      #pragma managed  
#pragma unmanaged  
#pragma managed([push,] on | off)  
#pragma managed(pop)  
```  
  
## <a name="remarks"></a>Примечания  
 [/CLR](../build/reference/clr-common-language-runtime-compilation.md) параметр компилятора предоставляет управление доступом на уровне модуля для компиляции функции управляемый или неуправляемый.  
  
 Неуправляемая функция компилируется для собственной платформы, и среда CLR передает выполнение этой части программы в собственную платформу.  
  
 Функции компилируются как управляемые по умолчанию при **/CLR** используется.  
  
 При применении этих директив pragma выполните следующие действия.  
  
-   Добавляйте директиву #pragma перед функцией, а не в теле функции.  
  
-   Добавьте директиву pragma после операторов `#include`. Не используйте эти директивы pragma перед операторами `#include`.  
  
 Компилятор игнорирует `managed` и `unmanaged` директивы pragma Если **/CLR** при компиляции не используется.  
  
 При создании экземпляра шаблонной функции режим ее компиляции (управляемый или неуправляемый код) определяется состоянием этой директивы #pragma в момент определения шаблона.  
  
 Дополнительные сведения см. в разделе [Инициализация смешанных сборок](../dotnet/initialization-of-mixed-assemblies.md).  
  
## <a name="example"></a>Пример  
  
```cpp  
// pragma_directives_managed_unmanaged.cpp  
// compile with: /clr  
#include <stdio.h>  
  
// func1 is managed  
void func1() {  
   System::Console::WriteLine("In managed function.");  
}  
  
// #pragma unmanaged  
// push managed state on to stack and set unmanaged state  
#pragma managed(push, off)  
  
// func2 is unmanaged  
void func2() {  
   printf("In unmanaged function.\n");  
}  
  
// #pragma managed  
#pragma managed(pop)  
  
// main is managed  
int main() {  
   func1();  
   func2();  
}  
```  
  
```Output  
In managed function.  
In unmanaged function.  
```  
  
## <a name="see-also"></a>См. также  
 [Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)