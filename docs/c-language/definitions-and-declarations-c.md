---
title: "Определения и объявления (C) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "функции экспорта"
ms.assetid: d150395a-89d4-4298-9ac4-08f84fe1261c
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Определения и объявления (C)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Интерфейс DLL относится ко всем элементам \(функциям и данным\), которые, как известно, должны экспортироваться некоторой программой в системе, т. е. ко всем элементам, объявленным как **dllimport** или `dllexport`.  Во всех объявлениях, включенных в интерфейсе DLL, должен указываться атрибут **dllimport** или `dllexport`.  Однако определение может задавать только атрибут `dllexport`.  Например, следующее определение функции вызовет ошибку компилятора.  
  
```  
#define DllImport   __declspec( dllimport )  
#define DllExport   __declspec( dllexport )  
  
DllImport int func()    /* Error; dllimport prohibited in */  
                        /* definition. */  
{  
   return 1;  
}  
```  
  
 Показанный ниже код также вызовет ошибку.  
  
```  
#define DllImport   __declspec( dllimport )  
#define DllExport   __declspec( dllexport )  
  
DllImport int i = 10;      /* Error; this is a definition. */  
```  
  
 Однако следующий синтаксис правильный.  
  
```  
#define DllImport   __declspec( dllimport )  
#define DllExport   __declspec( dllexport )  
  
DllExport int i = 10;      /* Okay: this is an export definition. */  
```  
  
 Использование атрибута `dllexport` подразумевает определение, а использование атрибута **dllimport** — объявление.  Для обеспечения объявления ключевое слово `extern` следует использовать с аргументом `dllexport`; в противном случае подразумевается определение.  
  
```  
#define DllImport   __declspec( dllimport )  
#define DllExport   __declspec( dllexport )  
  
extern DllImport int k;   /* These are correct and imply */  
Dllimport int j;          /* a declaration. */      
```  
  
 **Завершение блока, относящегося только к системам Microsoft**  
  
## См. также  
 [Функции импорта и экспорта DLL](../Topic/DLL%20Import%20and%20Export%20Functions.md)