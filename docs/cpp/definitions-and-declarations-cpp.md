---
title: "Определения и объявления (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
ms.assetid: 56b809c0-e602-4f18-9ca5-cd7a8fbaaf30
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Определения и объявления (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Блок, относящийся только к системам Microsoft  
 Интерфейс DLL относится ко всем элементам \(функциям и данным\), которые, как известно, должны экспортироваться некоторой программой в системе, т. е. ко всем элементам, объявленным как **dllimport** или `dllexport`.  Во всех объявлениях, включенных в интерфейсе DLL, должен указываться атрибут **dllimport** или `dllexport`.  Однако в определении должен указываться только атрибут `dllexport`.  Например, следующее определение функции вызовет ошибку компилятора.  
  
```  
__declspec( dllimport ) int func() {   // Error; dllimport  
                                    // prohibited on definition.  
   return 1;  
}  
```  
  
 Показанный ниже код также вызовет ошибку.  
  
```  
#define DllImport   __declspec( dllimport )  
  
__declspec( dllimport ) int i = 10;  // Error; this is a  
                                     // definition.  
```  
  
 Однако следующий синтаксис правильный.  
  
```  
__declspec( dllexport ) int i = 10;     // Okay--export definition  
```  
  
 Использование атрибута `dllexport` подразумевает определение, а использование атрибута **dllimport** — объявление.  Для обеспечения объявления ключевое слово `extern` следует использовать с аргументом `dllexport`; в противном случае подразумевается определение.  Таким образом, приведенные ниже примеры правильны.  
  
```  
#define DllImport   __declspec( dllimport )  
#define DllExport   __declspec( dllexport )  
  
extern DllImport int k; // These are both correct and imply a  
DllImport int j;        // declaration.  
```  
  
 В следующих примерах поясняются предшествующие.  
  
```  
static __declspec( dllimport ) int l; // Error; not declared extern.  
  
void func() {  
    static __declspec( dllimport ) int s;  // Error; not declared  
                                           // extern.  
    __declspec( dllimport ) int m;         // Okay; this is a   
                                           // declaration.  
    __declspec( dllexport ) int n;         // Error; implies external  
                                           // definition in local scope.  
    extern __declspec( dllimport ) int i;  // Okay; this is a  
                                           // declaration.  
    extern __declspec( dllexport ) int k;  // Okay; extern implies  
                                           // declaration.  
    __declspec( dllexport ) int x = 5;     // Error; implies external  
                                           // definition in local scope.  
}  
```  
  
## Завершение блока, относящегося только к системам Microsoft  
  
## См. также  
 [dllexport, dllimport](../cpp/dllexport-dllimport.md)