---
title: "Метод WeakReference::Resolve | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::WeakReference::Resolve"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Resolve - метод"
ms.assetid: fc65a4b7-48a0-4d64-a793-37f566fdd8e7
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Метод WeakReference::Resolve
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Предназначено для поддержки инфраструктуры WRL, а не для непосредственного использования в коде.  
  
## Синтаксис  
  
```  
  
STDMETHOD(Resolve)  
   (REFIID riid,   
   _Deref_out_opt_ IInspectable **ppvObject  
);  
```  
  
#### Параметры  
 `riid`  
 Идентификатор интерфейса.  
  
 `ppvObject`  
 Когда эта операция завершена, копия текущей строгой ссылки, если число строгих ссылок отлично от нуля.  
  
## Возвращаемое значение  
  
-   S\_OK, если операция выполнена успешно и число строгих ссылок равно нулю.  Параметр `ppvObject` принимает значение `nullptr`.  
  
-   S\_OK, если операция выполнена успешно и число строгих ссылок не равно нулю.  Параметру `ppvObject` задана строгая ссылка.  
  
-   В противном случае — значение HRESULT, указывающее причину неудачного завершения этой операции.  
  
## Заметки  
 Задает определенный указатель на значение текущей строгой ссылки, если число строгих ссылок отлично от нуля.  
  
## Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL::Details  
  
## См. также  
 [Класс WeakReference](../windows/weakreference-class1.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)