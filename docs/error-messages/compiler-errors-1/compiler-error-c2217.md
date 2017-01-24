---
title: "Ошибка компилятора C2217 | Microsoft Docs"
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
  - "C2217"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2217"
ms.assetid: 1ce1e3f5-4171-4376-804d-967f7e612935
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2217
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"attribute1" требует наличия "attribute2"  
  
 Первый атрибут функции требует наличия второго атрибута.  
  
### Чтобы устранить ошибку, следует проверить следующие возможные причины ее возникновения.  
  
1.  Функция обработки прерывания \(`__interrupt`\) описана как `near`.  Функции обработки прерываний должны иметь значение `far`.  
  
2.  Функция обработки прерывания описана с помощью `__stdcall` или `__fastcall`.  Функции обработки прерываний должны использовать соглашения о вызове языка C.  
  
## Пример  
 Ошибка C2217 также может возникнуть, если предпринята попытка привязки делегата к функции CLR, принимающей различные номера аргументов.  Если функция имеет перегруженный массив e param, то используйте его вместо нее.  В следующем примере формируется сообщение об ошибке C2217.  
  
```  
// C2217.cpp  
// compile with: /clr  
using namespace System;  
delegate void MyDel(String^, Object^, Object^, ...);   // C2217  
delegate void MyDel2(String ^, array<Object ^> ^);   // OK  
  
int main() {  
   MyDel2^ wl = gcnew MyDel2(Console::WriteLine);  
   array<Object ^ > ^ x = gcnew array<Object ^>(2);  
   x[0] = safe_cast<Object^>(0);  
   x[1] = safe_cast<Object^>(1);  
  
   // wl("{0}, {1}", 0, 1);  
   wl("{0}, {1}", x);  
}  
```