---
title: "Ошибка компилятора CS0061 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0061"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0061"
ms.assetid: 8dfc57a9-653d-4902-a88c-92032ba64024
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Ошибка компилятора CS0061
Несогласованность по доступности: доступность базового интерфейса "интерфейс\_1" ниже доступности интерфейса "интерфейс\_2"  
  
 [Открытая](../Topic/public%20\(C%23%20Reference\).md) конструкция должна возвращать общедоступный объект.  
  
 Доступность интерфейса не может быть снижена в производном интерфейсе. Дополнительные сведения см. в разделах [Интерфейсы](../Topic/Interfaces%20\(C%23%20Programming%20Guide\).md) и [Модификаторы доступа](../Topic/Access%20Modifiers%20\(C%23%20Programming%20Guide\).md).  
  
 В следующем примере возникает ошибка CS0061.  
  
```  
// CS0061.cs // compile with: /target:library internal interface A {} public interface AA : A {}  // CS0061 // OK public interface B {} internal interface BB : B {} internal interface C {} internal interface CC : C {}  
```