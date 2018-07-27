---
title: Предупреждение (уровень 4) C4210 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4210
dev_langs:
- C++
helpviewer_keywords:
- C4210
ms.assetid: f8600adf-dfe2-4022-a37a-3d4997641dfd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e1a376eb8bb9c5dffe5cfd4bc34c720c7e0acf41
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33292491"
---
# <a name="compiler-warning-level-4-c4210"></a>Предупреждение компилятора (уровень 4) C4210
использовано нестандартное расширение: функция видима в пределах файла  
  
 С расширениями Майкрософт по умолчанию ([/Ze](../../build/reference/za-ze-disable-language-extensions.md)), объявления функций имеют область видимости файла.  
  
```  
// C4210.c  
// compile with: /W4 /c  
void func1()  
{  
   extern int func2( double );   // C4210 expected  
}  
  
int main()  
{  
   func2( 4 );   //  /Ze passes 4 as type double  
}                //  /Za passes 4 as type int  
```  
  
 Этот модуль может помешать кода в другие компиляторы.