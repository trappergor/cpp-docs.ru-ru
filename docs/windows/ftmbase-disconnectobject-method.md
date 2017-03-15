---
title: "Метод FtmBase::DisconnectObject | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ftm/Microsoft::WRL::FtmBase::DisconnectObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DisconnectObject - метод"
ms.assetid: 33253eec-3a65-4e72-8525-0249245a4790
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# Метод FtmBase::DisconnectObject
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Принудительно освобождает все внешние подключения к объекту.  Сервер объекта вызывает реализацию этого метода объекта до завершения работы.  
  
## Синтаксис  
  
```  
STDMETHODIMP DisconnectObject(  
   __in DWORD dwReserved  
) override;  
```  
  
#### Параметры  
 `dwReserved`  
 Зарезервировано для будущего использования; должно быть нулем.  
  
## Возвращаемое значение  
 Значение S\_ОК в случае успеха; в противном случае — значение HRESULT, указывающее на ошибку.  
  
## Требования  
 **Заголовок:** ftm.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс FtmBase](../windows/ftmbase-class.md)