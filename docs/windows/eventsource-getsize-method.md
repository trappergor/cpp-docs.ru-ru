---
title: "Метод EventSource::GetSize | Microsoft Docs"
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
  - "event/Microsoft::WRL::EventSource::GetSize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetSize - метод"
ms.assetid: 7825aab5-1a6b-465f-9159-3a6684142d1f
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Метод EventSource::GetSize
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Возвращает число обработчиков событий, связанных с текущим объектом EventSource  
  
## <a name="syntax"></a>Синтаксис  
  
```  
size_t GetSize() const;  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Количество обработчиков событий в [targets_](../Topic/EventSource::targets_%20Data%20Member.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** event.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также раздел  
 [Класс EventSource](../windows/eventsource-class.md)