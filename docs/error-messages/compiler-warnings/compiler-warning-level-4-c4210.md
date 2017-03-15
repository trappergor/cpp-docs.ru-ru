---
title: "Предупреждение компилятора (уровень 4) C4210 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4210"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4210"
ms.assetid: f8600adf-dfe2-4022-a37a-3d4997641dfd
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Предупреждение компилятора (уровень 4) C4210
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

нестандартное расширение: функция видима в пределах файла  
  
 При использовании расширений Майкрософт по умолчанию \([\/Ze](../../build/reference/za-ze-disable-language-extensions.md)\) объявления функций имеют область видимости в пределах файла.  
  
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
  
 Это расширение может предотвратить перенос кода в другие компиляторы.