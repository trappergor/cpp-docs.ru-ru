---
title: "delete - оператор (CRT) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr120.dll"
  - "msvcr100.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
apitype: "DLLExport"
f1_keywords: 
  - "delete"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "delete - оператор"
  - "скалярное удаление"
ms.assetid: bcd0066a-0022-45f5-af4c-9007c64a6b89
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# delete - оператор (CRT)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Освобождает размещенный в памяти блок.  
  
## Синтаксис  
  
```  
  
      void __cdecl operator delete(  
   void * object  
);  
void __cdecl operator delete(  
   void * object,   
   void * memory  
) throw();  
void __cdecl operator delete(  
   void * object,   
   const std::nothrow_t&  
) throw();  
```  
  
#### Параметры  
 *память*  
 Освобождаемая область памяти.  
  
 *object*  
 Указатель на удаляемый объект.  
  
## Заметки  
 Эта форма **оператора delete** известна как скалярное delete, в отличие от векторной формы delete \([оператор delete&#91;&#93;](../c-runtime-library/delete-operator-crt.md)\).  
  
 **оператор delete** освобождает память, выделенную с помощью [оператора new](../c-runtime-library/operator-new-crt.md).  
  
 Первая форма данного оператора известна как неразмещающая форма.  Вторая и третья формы этого оператора обычно не вызываются из кода и существуют только чтобы дать компилятору возможность соответствующего удаления, когда размещение new не выполняется.  
  
 Первая форма оператора определяется компилятором и не требует включения new.h в программу.  
  
 За исключением возможности разрешить или запретить генерацию исключений, CRT **оператор delete** работает подобно [оператору delete](../Topic/operator%20delete%20\(%3Cnew%3E\).md) в стандартной библиотеке C\+\+.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|**удаление**|\<new.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../c-runtime-library/compatibility.md) во введении.  
  
## Библиотеки  
 Все версии [библиотек времени выполнения C](../c-runtime-library/crt-library-features.md).  
  
## Пример  
 В разделе [оператор new](../c-runtime-library/operator-new-crt.md) приведены примеры использования оператора **delete**.  
  
## См. также  
 [Выделение памяти](../c-runtime-library/memory-allocation.md)