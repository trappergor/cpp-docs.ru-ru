---
title: "Компоновка статической константы Int больше не является литералом | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "константы, объявление"
  - "интегральные константные выражения"
  - "атрибут-литерал [C++]"
ms.assetid: d2a5e3d2-ffb0-4b61-8114-bec5993a1195
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Компоновка статической константы Int больше не является литералом
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Объявление постоянного члена класса изменилось с управляемых расширений C\+\+ на [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)].  
  
 Целочисленные члены `static const` по\-прежнему поддерживаются, однако их атрибут компоновки изменился.  Прежний атрибут компоновки теперь выражается целочисленным членом\-литералом.  В качестве примера рассмотрим следующий класс управляемых расширений.  
  
```  
public __gc class Constants {  
public:  
   static const int LOG_DEBUG = 4;  
};  
```  
  
 Этот код создает следующие основные атрибуты CIL для поля \(обратите внимание на атрибут\-литерал\).  
  
```  
.field public static literal int32   
modopt([Microsoft.VisualC]Microsoft.VisualC.IsConstModifier) STANDARD_CLIENT_PRX = int32(0x00000004)  
```  
  
 Этот код по\-прежнему может компилироваться в новом синтаксисе.  
  
```  
public ref class Constants {  
public:  
   static const int LOG_DEBUG = 4;  
};  
```  
  
 Однако он теперь не генерирует атрибут\-литерал, и поэтому не отображается как константа в среде CLR.  
  
```  
.field public static int32 modopt([Microsoft.VisualC]Microsoft.VisualC.IsConstModifier) STANDARD_CLIENT_PRX = int32(0x00000004)  
```  
  
 Чтобы объявление имело такой же межъязыковой атрибут\-литерал, это объявление нужно заменить новым поддерживаемым членом данных `literal`, как показано ниже.  
  
```  
public ref class Constants {  
public:  
   literal int LOG_DEBUG = 4;  
};  
```  
  
## См. также  
 [Объявления членов в пределах класса или интерфейса \(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [literal](../windows/literal-cpp-component-extensions.md)