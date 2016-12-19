---
title: "Метод WeakRef::CopyTo | Microsoft Docs"
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
  - "client/Microsoft::WRL::WeakRef::CopyTo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CopyTo - метод"
ms.assetid: f83de6da-b3d4-41a6-9845-cd725ecf3b75
caps.latest.revision: 5
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Метод WeakRef::CopyTo
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Присваивает указатель на интерфейс \(при его наличии\) указанной переменной указателя.  
  
## Синтаксис  
  
```  
HRESULT CopyTo(  
   REFIID riid,  
   _Deref_out_ IInspectable** ptr  
);  
  
template<  
   typename U  
>  
HRESULT CopyTo(  
   _Deref_out_ U** ptr  
);  
  
HRESULT CopyTo(  
   _Deref_out_ IWeakReference** ptr  
);  
```  
  
#### Параметры  
 `U`  
 Указатель на интерфейс IInspectable. Если параметр `U` не получен из IInspectable, возникает ошибка.  
  
 `riid`  
 Идентификатор интерфейса. Если параметр `riid` не получен из **IWeakReference**, возникает ошибка.  
  
 `ptr`  
 Двойной косвенный указатель на IInspectable или IWeakReference.  
  
## Возвращаемое значение  
 Значение S\_OK, если операция завершилась успешно; в противном случае — значение HRESULT, описывающее тип сбоя. Дополнительные сведения см. в разделе "Замечания".  
  
## Примечания  
 Возвращаемое значение S\_OK означает, что эта операция завершилась успешно, но не указывает, была ли слабая ссылка разрешена в строгую ссылку. Если возвращается значение S\_OK, проверьте, содержит ли параметр `p` строгую ссылку, то есть не имеет ли параметр `p` значение `nullptr`.  
  
 Начиная с пакета SDK для Windows 10 этот метод не устанавливает экземпляр WeakRef в значение `nullptr`, если не удалось получить слабую ссылку, поэтому следует избегать использования кода проверки ошибок, который проверяет наличие `nullptr` для WeakRef. Вместо этого проверьте возвращенное значение HRESULT, чтобы узнать, успешно ли выполнен метод, или проверьте `ptr` на наличие `nullptr`.  
  
## Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс WeakRef](../windows/weakref-class.md)