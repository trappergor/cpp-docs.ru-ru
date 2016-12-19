---
title: "Метод FtmBase::UnmarshalInterface | Microsoft Docs"
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
  - "ftm/Microsoft::WRL::FtmBase::UnmarshalInterface"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "UnmarshalInterface - метод"
ms.assetid: 6850a621-e9a6-4001-bc1e-bd5d1b121adc
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Метод FtmBase::UnmarshalInterface
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Инициализирует вновь созданный прокси\-сервер и возвращает указатель интерфейса к этому прокси\-серверу.  
  
## Синтаксис  
  
```  
STDMETHODIMP UnmarshalInterface(  
   __in IStream *pStm,  
   __in REFIID riid,  
   __deref_out void **ppv  
) override;  
```  
  
#### Параметры  
 `pStm`  
 Указатель на поток, из которого указатель интерфейса должен быть демаршалирован.  
  
 `riid`  
 Ссылка на идентификатор интерфейса для демаршалинга.  
  
 `ppv`  
 Если эта операция завершена, адрес переменной указателя, получающей указатель интерфейса, запрошенного в `riid`.  Если операция выполнена успешно, то \*`ppv` содержит запрошенный интерфейсный указатель на интерфейса для демаршалинга.  
  
## Возвращаемое значение  
 S\_OK, если операция завершилась удачно; в противном случае E\_FAIL или E\_NOINTERFACE.  
  
## Требования  
 **Заголовок:** ftm.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс FtmBase](../windows/ftmbase-class.md)