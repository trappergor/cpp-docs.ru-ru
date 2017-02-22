---
title: "Ошибка компилятора C3825 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3825"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3825"
ms.assetid: 18e204a1-f26e-42c6-8d74-2b49cc95f940
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Ошибка компилятора C3825
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

class: управляемый класс или класс WinRT может поддерживать только управляемые события или события WinRT  
  
 В управляемых классах поддерживаются только события .NET.  В классах среды выполнения Windows поддерживаются только события среды выполнения Windows.  Чтобы устранить эту ошибку в управляемом коде, измените параметр типа `event_source` и `event_receiver` с `native` на `managed`.  Можно также удалить атрибут.  
  
## Пример  
 В следующем примере показано возникновение ошибки C3825 и приводятся сведения по ее устранению.  
  
```  
// C3825a.cpp  
// compile with: /clr  
public delegate void del1();  
  
[event_source(native)]           // To fix, change 'native' to 'managed' or delete this line  
ref class CEventSrc  
{  
public:  
   event del1^ event1;       // C3825  
  
   void FireEvents() {  
      event1();  
   }  
};  
  
[event_receiver(native)]         // To fix, change 'native' to 'managed' or delete this line  
ref class CEventRec  
{  
public:  
   void handler1()  
   {  
      System::Console::WriteLine("Executing handler1().\n");  
   }  
   void HookEvents(CEventSrc^ pSrc)   
   {  
      pSrc->event1 += gcnew del1(this, &CEventRec::handler1);  
   }  
   void UnhookEvents(CEventSrc^ pSrc)   
   {  
      pSrc->event1 -= gcnew del1(this, &CEventRec::handler1);  
   }  
};  
  
int main()   
{  
   CEventSrc^ pEventSrc = gcnew CEventSrc;  
   CEventRec^ pEventRec = gcnew CEventRec;  
   pEventRec->HookEvents(pEventSrc);  
   pEventSrc->FireEvents();  
   pEventRec->UnhookEvents(pEventSrc);  
}  
```