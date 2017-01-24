---
title: "Ошибка компилятора C3072 | Microsoft Docs"
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
  - "C3072"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3072"
ms.assetid: cdd5cb6b-c478-4698-adfa-c40188d34a18
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3072
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

оператор "оператор" неприменим к экземпляру ссылочного класса  
  
 Используйте унарный оператор `operator` для преобразования экземпляра ссылочного класса в тип дескриптора.  
  
 Для типа CLR нужны операторы CLR, а не неуправляемые \(или стандартные\) операторы.  Для получения дополнительной информации см. [Оператор отслеживания ссылок](../../windows/tracking-reference-operator-cpp-component-extensions.md).  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C3072:  
  
```  
// C3072.cpp  
// compile with: /clr  
ref class R {};  
  
int main() {  
   R r1;  
   R^ r2 = &r1;   // C3072  
   R^ r3 = %r1;   // OK  
}  
```