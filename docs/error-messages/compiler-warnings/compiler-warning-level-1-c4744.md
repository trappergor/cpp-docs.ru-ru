---
title: "Предупреждение компилятора (уровень 1) C4744 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4744"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4744"
ms.assetid: f2a7d0b5-afd5-4926-abc3-cfbd367e3ff5
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 1) C4744
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"переменная" имеет различные типы в "файле1" и "файле2": "тип1" и "тип2"  
  
 Внешняя переменная, на которую указывает ссылка или которая определена в двух файлах, имеет в этих файлах различные типы.  Для решения данной проблемы необходимо либо сделать определения типа одинаковыми, либо изменить имя переменной в одном из файлов.  
  
 Предупреждение C4744 вызывается, только если файлы были скомпилированы с помощью \/GL.  Для получения дополнительной информации см. [\/GL \(оптимизация всей программы\)](../../build/reference/gl-whole-program-optimization.md).  
  
> [!NOTE]
>  Предупреждение C4744 обычно возникает в файлах C \(не C\+\+\), поскольку в C\+\+ к имени переменной приписываются сведения о типе.  При компиляции нижеприведенного примера на C\+\+, возникнет ошибка компоновщика LNK2019.  
  
## Пример  
 В примере содержится первое определение.  
  
```  
// C4744.c  
// compile with: /c /GL  
int global;  
```  
  
## Пример  
 В следующем примере возникает предупреждение C4744.  
  
```  
// C4744b.c  
// compile with: C4744.c /GL /W1  
// C4744 expected  
#include <stdio.h>  
  
extern unsigned global;  
  
main()   
{  
    printf_s("%d\n", global);  
}  
```