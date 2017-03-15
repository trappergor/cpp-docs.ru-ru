---
title: "Метод ComPtr::CopyTo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::ComPtr::CopyTo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CopyTo - метод"
ms.assetid: 8801bc49-6db4-4393-a55f-a701ae3b8718
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# Метод ComPtr::CopyTo
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Копирует текущий или указанный интерфейс, связанный с этим ComPtr, в заданный выходной указатель.  
  
## Синтаксис  
  
```  
HRESULT CopyTo(  
   _Deref_out_ InterfaceType** ptr  
);  
  
HRESULT CopyTo(  
   REFIID riid,  
   _Deref_out_ void** ptr  
) const;  
template<  
   typename U  
>  
  
HRESULT CopyTo(  
   _Deref_out_ U** ptr  
) const;  
```  
  
#### Параметры  
 `U`  
 Имя типа.  
  
 `ptr`  
 Когда эта операция будет завершена, указатель на запрошенный интерфейс.  
  
 `riid`  
 Идентификатор интерфейса.  
  
## Возвращаемое значение  
 S\_OK, если операция завершилась удачно; в противном случае значение HRESULT, показывающее причину завершения ошибкой неявной операции QueryInterface.  
  
## Примечания  
 Первая функция возвращает копию указателя на интерфейс, связанный с этим ComPtr.  Эта функция всегда возвращает значение S\_OK.  
  
 Вторая функция выполняет операцию QueryInterface на интерфейсе, связанном с этим ComPtr, для интерфейса, указанного в параметре `riid`.  
  
 Третья функция выполняет операцию QueryInterface в интерфейсе, связанном с этим ComPtr, для базового интерфейса параметра `U`.  
  
## Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс ComPtr](../windows/comptr-class.md)