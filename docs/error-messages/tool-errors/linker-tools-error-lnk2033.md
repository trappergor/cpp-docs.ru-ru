---
title: "Ошибка средств компоновщика LNK2033 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2033"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2033"
ms.assetid: d61db467-9328-4788-bf54-e2a20537f13f
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# Ошибка средств компоновщика LNK2033
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Неразрешенная лексема TypeRef для типа "тип"  
  
 Тип не имеет определения в метаданных MSIL.  
  
 Ошибка LNK2033 может возникнуть при компилировании с **\/clr:safe**, когда в модуле MSIL присутствует только переадресовывающее объявление, при котором в модуле MSIL имеется ссылка на тип.  
  
 Тип необходимо определить в **\/clr:safe**.  
  
 Для получения дополнительной информации см. [\/clr \(компиляция CLR\)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## Пример  
 Следующий пример приводит к возникновению ошибки LNK2033.  
  
```  
// LNK2033.cpp  
// compile with: /clr:safe  
// LNK2033 expected  
ref class A;  
ref class B {};  
  
int main() {  
   A ^ aa = nullptr;  
   B ^ bb = nullptr;   // OK  
};  
```