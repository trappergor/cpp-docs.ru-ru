---
title: "Метод DeferrableEventArgs::GetDeferral | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: ef6dc7c5-b0be-4b85-8507-d3fd97f2185d
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Метод DeferrableEventArgs::GetDeferral
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Возвращает ссылку на объект [Задержка](http://go.microsoft.com/fwlink/?LinkId=526520), который представляет отложенное событие.  
  
## Синтаксис  
  
```cpp  
HRESULT GetDeferral([out, retval] Windows::Foundation::IDeferral** result)  
```  
  
#### Параметры  
 `result`  
 Указатель, который будет ссылаться на объект [Задержка](http://go.microsoft.com/fwlink/?LinkId=526520) после завершения вызова.  
  
## Возвращаемое значение  
 Значение S\_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.  
  
## Заметки  
 Пример кода см. в разделе [Класс DeferrableEventArgs](../windows/deferrableeventargs-class.md).  
  
## Требования  
 **Заголовок:** event.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс DeferrableEventArgs](../windows/deferrableeventargs-class.md)