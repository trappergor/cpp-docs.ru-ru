---
title: "Предупреждение компилятора (уровень 1) C4581 | Microsoft Docs"
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
  - "C4581"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4581"
ms.assetid: 598bcd87-257d-4eb3-94e4-15bb31aadc99
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 1) C4581
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

нерекомендуемое поведение: "строка 1" заменяется на "строка 2" для обработки атрибута  
  
 Данная ошибка может возникать в результате действий по обеспечению совместимости компилятора с Visual C\+\+ 2005: проверка параметров для атрибутов Visual C\+\+.  
  
 В предыдущих версиях значения атрибутов принимались вне зависимости от того, были они заключены в кавычки или нет.  Если значение является перечислением, оно не должно заключаться в кавычки.  
  
## Пример  
 В следующем примере продемонстрировано возникновение ошибки C4581.  
  
```  
// C4581.cpp  
// compile with: /c /W1  
#include "unknwn.h"  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IMyI : IUnknown {};  
  
[coclass, uuid(12345678-1111-2222-3333-123456789012), threading("free")]   // C4581  
// try the following line instead  
// [coclass, uuid(12345678-1111-2222-3333-123456789012), threading(free)]  
class CSample : public IMyI {};  
```