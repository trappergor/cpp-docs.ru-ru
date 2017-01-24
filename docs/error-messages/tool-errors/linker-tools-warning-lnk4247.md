---
title: "Предупреждение средств компоновщика LNK4247 | Microsoft Docs"
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
  - "LNK4247"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4247"
ms.assetid: 085d7fdf-9eaf-4641-8473-6eaadd073c7b
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение средств компоновщика LNK4247
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

точка входа "декорированное\_имя\_функции" уже имеет атрибут потока; "атрибут" пропущен  
  
 Точка входа, указанная с помощью параметра [\/ENTRY \(символ точки входа\)](../../build/reference/entry-entry-point-symbol.md), имела потоковый атрибут, но при этом также был указан параметр [\/CLRTHREADATTRIBUTE \(Установка атрибута потока среды CLR\)](../../build/reference/clrthreadattribute-set-clr-thread-attribute.md) с другой потоковой моделью.  
  
 Компоновщик пропускает значение, указанное с помощью параметра \/CLRTHREADATTRIBUTE.  
  
 Чтобы устранить это предупреждение:  
  
-   не используйте при построении параметр \/CLRTHREADATTRIBUTE;  
  
-   удалите атрибут из файла исходного кода;  
  
-   удалите атрибут из исходного кода и параметр \/CLRTHREADATTRIBUTE из построения, и используйте потоковую модель среды CLR по умолчанию;  
  
-   измените значение, заданное с помощью параметра \/CLRTHREADATTRIBUTE, чтобы оно соответствовало атрибуту в исходном коде;  
  
-   измените атрибут в исходном коде, чтобы он соответствовал значению, заданному с помощью параметра \/CLRTHREADATTRIBUTE.  
  
 Следующий пример приводит к возникновению предупреждения LNK4247  
  
```  
// LNK4247.cpp  
// compile with: /clr /c  
// post-build command: link /CLRTHREADATTRIBUTE:STA LNK4247.obj /entry:functionTitle /SUBSYSTEM:Console  
 [System::MTAThreadAttribute]  
void functionTitle (){}  
```