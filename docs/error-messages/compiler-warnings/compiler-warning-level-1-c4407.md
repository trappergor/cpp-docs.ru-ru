---
title: "Предупреждение компилятора (уровень 1) C4407 | Microsoft Docs"
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
  - "C4407"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4407"
ms.assetid: 32bc2c21-363a-4bb8-b486-725faeaededc
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 1) C4407
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

приведение между разными представлениями указателя на член; компилятор может создать неправильный код  
  
 Обнаружено неправильное привидение.  
  
 Ошибка C4407 также может возникать вследствие действий по обеспечению совместимости компилятора с Visual C\+\+ 2005.  Указатель теперь требуется полное имя и оператора взятия адреса \(&\).  
  
 Предупреждение C4407 может возникать, если выполняется приведение указателя на член с множественным наследованием к указателю на член с единичным наследованием.  Иногда это может сработать, а иногда — нет, так как представление указателя на член с единичным наследованием не содержит необходимой для этого информации.  Помочь может компиляция с параметром **\/vmm** \(дополнительные сведения см. в разделе [\/vmm, \/vms и \/vmv \(представление общего назначения\)](../../build/reference/vmm-vms-vmv-general-purpose-representation.md)\).  Можно также попытаться реорганизовать базовые классы; компилятор обнаружит потерю информации при преобразовании, так как базовый класс располагается по ненулевому смещению от производного.  
  
 Следующий пример приводит к возникновению ошибки C4407:  
  
```  
// C4407.cpp  
// compile with: /W1 /c  
struct C1 {};  
struct C2 {};  
struct C3 : C1, C2 {};  
  
typedef void(C3::*PMF_C3)();  
typedef void(C2::*PMF_C2)();  
  
PMF_C2 f1(PMF_C3 pmf) {  
   return (PMF_C2)pmf;   // C4407, change type of cast,  
   // or reverse base class inheritance of C3 (i.e. : C2, C1)  
}  
```