---
title: "Метод ComPtr::AsIID | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::ComPtr::AsIID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AsIID - метод"
ms.assetid: d5a3cdb2-796d-4410-966a-847c0e8fb226
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Метод ComPtr::AsIID
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Возвращает объект ComPtr, представляющий интерфейс, определенный указанным идентификатором интерфейса.  
  
## Синтаксис  
  
```  
WRL_NOTHROW HRESULT AsIID(  
   REFIID riid,  
   _Out_ ComPtr<IUnknown>* p  
) const;  
```  
  
#### Параметры  
 `riid`  
 Идентификатор интерфейса.  
  
 `p`  
 Если поддерживается — двойной косвенный указатель на интерфейс, определяемый параметром `riid`; в противном случае — указатель на IUnknown.  
  
## Возвращаемое значение  
 Значение S\_ОК в случае успеха; в противном случае — значение HRESULT, указывающее на ошибку.  
  
## Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс ComPtr](../windows/comptr-class.md)