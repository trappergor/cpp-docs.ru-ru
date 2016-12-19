---
title: "оператор delete(CRT) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr90.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr120.dll"
  - "msvcr100.dll"
  - "msvcr80.dll"
apitype: "DLLExport"
f1_keywords: 
  - "delete[]"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Оператор delete[]"
  - "вектор delete"
ms.assetid: e91bd0df-3815-40ca-950a-67b470518aed
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# оператор delete(CRT)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Освобождает размещенный в памяти блок.  
  
## Синтаксис  
  
```  
  
      void __cdecl operator delete[](void * object);  
void __cdecl operator delete[](void * object,   
   void * memory) throw();  
void __cdecl operator delete[](void * object,   
   const std::nothrow_t&) throw();  
```  
  
#### Параметры  
 *память*  
 Освобождаемая область памяти.  
  
 *object*  
 Указатель на удаляемый объект.  
  
## Заметки  
 Эта форма **оператора delete** известна как векторный delete, в отличие от скалярной формы delete \([оператор delete](../c-runtime-library/operator-delete-crt.md)\).  
  
 **оператор** `delete[]` освобождает память, выделенную [оператором new&#91;&#93;](../c-runtime-library/new-operator-crt.md).  
  
 Первая форма данного оператора известна как неразмещающая форма.  Вторая и третья формы этого оператора обычно не вызываются из кода и существуют только чтобы дать компилятору возможность соответствующего удаления, когда размещение new не выполняется.  
  
 Первая форма оператора определяется компилятором и не требует включения new.h в программу.  
  
 За исключением возможности разрешить или запретить генерацию исключений, CRT **оператор** `delete[]` работает подобно [оператору delete&#91;&#93;](../Topic/operator%20delete\(%3Cnew%3E\).md) в стандартной библиотеке C\+\+.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`delete[]`|\<new.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../c-runtime-library/compatibility.md) во введении.  
  
## Библиотеки  
 Все версии [библиотек времени выполнения C](../c-runtime-library/crt-library-features.md).  
  
## Пример  
 В разделе [оператор new&#91;&#93;](../c-runtime-library/new-operator-crt.md) приведены примеры использования оператора **delete**.  
  
## См. также  
 [Выделение памяти](../c-runtime-library/memory-allocation.md)