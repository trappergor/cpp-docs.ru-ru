---
title: "synchronize | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.synchronize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "synchronize attribute"
ms.assetid: 15fc8544-955d-4765-b3d5-0f619c8b3f40
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# synchronize
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Синхронизировать доступ к методу пристрелки.  
  
## Синтаксис  
  
```  
  
[synchronize]  
  
```  
  
## Заметки  
 **синхронизировать** Атрибут C\+\+ реализует поддержку синхронизировать метод пристрелки объекта.  Синхронизация обеспечивает несколько объектов для использования общего ресурса \(uri\) \(например метод класса\), отслеживая доступ метода пристрелки.  
  
 Код вставленный этим атрибутом вызовет соответствующее `Lock` метод \(заданный потоковой моделью\) в начале метода пристрелки.  При выйденн, метод `Unlock` автоматически вызывает.  Дополнительные сведения об этих функциях см. в разделе [CComAutoThreadModule:: блокировать](../Topic/CComAutoThreadModule::Lock.md)  
  
 Этот атрибут необходим [CoClass](../windows/coclass.md)"  [идентификатор progid](../Topic/progid.md)или  [vi\_progid](../windows/vi-progid.md) атрибут \(или другой атрибут, подразумевается одно из них\) также были применены к одному элементу.  Если отдельный атрибут используется, то остальные 2 автоматически применены.  Например, если **идентификатор progid** применяет  **vi\_progid** и  **CoClass** также применить.  
  
## Пример  
 Следующий код обеспечивает синхронизацию `UpdateBalance` метод   `CMyClass` объект.  
  
```  
// cpp_attr_ref_synchronize.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module(name="SYNC")];  
  
[coclass,  
 threading(both),  
 vi_progid("MyProject.MyClass"),  
 progid("MyProject.MyClass.1"),  
 uuid("7a7baa0d-59b8-4576-b754-79d07e1d1cc3")  
]  
class CMyClass {  
   float m_nBalance;  
  
   [synchronize]  
   void UpdateBalance(float nAdjust) {  
      m_nBalance += nAdjust;  
   }  
};  
```  
  
## Требования  
  
### Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|Метод класса, метод|  
|**Repeatable**|Нет|  
|**Обязательные атрибуты**|Одно или несколько из следующих значений: **CoClass**"  **идентификатор progid**или  **vi\_progid**.|  
|**Недопустимые атрибуты**|None|  
  
 Дополнительные сведения о контекстах атрибута см. в разделе [Контексты атрибута](../windows/attribute-contexts.md).  
  
## См. также  
 [COM Attributes](../Topic/COM%20Attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ru-ru/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)